---
author: roundcrisis
date: 2020-11-30 20:48:00+00:00
layout: single
classes: wide
title: Timer with Cats Effects
categories:
- scala
- cats-effects
---

Not so long ago, I had to add a feature that should run periodically as part of a web-server. I thought, no problem, I will use [`cats effects`](https://typelevel.org/cats-effect/datatypes/contextshift.html) that will run whatever I need on a separate thread and return once completed. I was wrong ...

My initial program looked something like this:

```
object TimerInitial extends IOApp {

  def periodicReminder(implicit contextShift: ContextShift[IO]): IO[Unit] = {
    println("from periodic ")
    timer.sleep(1.second).flatMap(_ => periodicReminder)
  }

  override def run(args: List[String]): IO[ExitCode] =
    for {
      _ <- IO(println(s"Before"))
      _ <- IO.shift *> periodicReminder
      _ <- IO(println("After"))
      _ <- IO.sleep(5.second)
      _ <- IO(println(s"end"))
    } yield ExitCode.Success

}

```
What I was trying to achieve was that it will print:

    Before 
    from periodic
    After
    from periodic 
    from periodic 
    from periodic 
    end 

Process finished with exit code 0


However what I got was:

    Before 
    from periodic 
    from periodic 
    from periodic 
    from periodic 

    //until I stopped execution

This is not ideal but why is this  happening? 
In the `for comprehension` there is a call to  [IO.shift](https://typelevel.org/cats-effect/datatypes/io.html#thread-shifting), and given the rest of the code, we switch context to where the method where we have a timer and there is nothing to bring us back to the context of the main `run` method. 


So I thought, maybe something can bring the context back, I tried `IO.delay` which Suspends a synchronous side effect in `IO`. Which is not really what I needed to do. 

```
object ThingWithTimer extends IOApp {
  def periodicReminder(implicit contextShift: ContextShift[IO]): IO[Unit] = IO.delay {
    println("from periodic ")
    timer.sleep(1.second).flatMap(_ => periodicReminder)
  }

  override def run(args: List[String]): IO[ExitCode] = {
    
    for {
      _ <- IO(println(s"Before"))
      _ <- IO.shift *> periodicReminder
      _ <- IO(println("After"))
      _ <- IO.sleep(5.second)
      _ <- IO(println(s"end"))
    } yield ExitCode.Success
  }

}

```
The results of running this were however a little closer to what I was looking for in that the context returned to the main `run` method:

    Before
    from periodic 
    After
    end

    Process finished with exit code 0


So, what we were looking for is a method called [`background`](https://github.com/typelevel/cats-effect/blob/series/2.x/core/shared/src/main/scala/cats/effect/IO.scala#L405) which returns a resource that will start execution of this IO in the background. Which is pretty perfect for the kind of task this needs to do.


```
object TimerBackground extends IOApp {

  def periodicReminder(implicit contextShift: ContextShift[IO]): IO[Unit] =
    for {
      _ <- IO(println("From periodic "))
      _ <- timer.sleep(1.second).flatMap(_ => periodicReminder)
    } yield ()  

  override def run(args: List[String]): IO[ExitCode] =
    (for {
      _ <- Resource.liftF(IO(println(s"Before ${ZonedDateTime.now()}")))

      _ <- periodicReminder.background
      _ <- Resource.liftF(IO(println("After")))
      _ <- Resource.liftF(IO.sleep(5.seconds))
      _ <- Resource.liftF(IO(println(s"end ")))
    } yield ()).use(_ => IO(ExitCode.Success))
}
```


And I think that is all for today, till the next time.