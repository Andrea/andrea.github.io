---
layout: post
title:  "Multithreading rendering in a game engine with C# - Double buffer implementation"
date:   2013-05-24 12:40:10
categories: ""
---

  <p>A game running at 60FPS needs to render every 16 milliseconds, meaning
  that all the logic for collision detection, animation, obstacle avoidance,
  physics, etc. must happen in that very short time. You also need to prepare
  for rendering and then send the instructions to the GPU. Multithreading see
  ms like a most reasonable option if you have more than one core available
  (and who doesn’t these days).</p>

  <p>One of the ways to do multithreading rendering in games is using a double
  buffer. At a high level the concept is simple: given two threads update and
  render, use one to fill a buffer with commands that have enough info to
  render(we’ll call them <strong>RenderCommands</strong>), once completed
  switch buffers while the other thread renders the RenderCommands in the
  original buffer.&nbsp;</p>

  <p>&nbsp;</p>

  <p><a href="http://altdevblogaday.com/wp-content/uploads/2011/07/04.png"
  target="_blank"><img height="33" src=
  "http://altdevblogaday.com/wp-content/uploads/2011/07/04.png" style=
  "margin:0 0 0 5px;" width="512"></a></p>

  <p>Graph and possibly a better explanation of double buffer from <a href=
  "http://bit.ly/110JuB3" title=
  "http://bit.ly/110JuB3">http://bit.ly/110JuB3</a></p>

  <p>You might be wondering what is a render command, well it’s the smallest
  amount of information we need to send to the GPU so that it can render what
  we want it to render. A Render command for a cube only engine (ie our engine
  can only draw cubes) can be as simple as:</p>

{% highlight c# %}
 public class RenderCommand
{
    public float Radius { get; set; }
    public Color Color { get; set; }
    public Matrix World { get; set; }
}
{% endhighlight %}
  <p>There are many ways to implement this double buffer technique. The
  implementation we are going to see in this example is based on Quake 3 source
  code using modern C# to implement it. Questions, comments and optimizations
  welcome :D. By the way, a really in-depth review of the code is available
  <a href="http://fabiensanglard.net/quake3/index.php" target=
  "_blank">here</a>.</p>

  <h3>The idea</h3>

  <p><em>The update thread is the red one and the render thread is the blue
  one.</em></p>

  <p><a href=
  "http://roundcrisis.files.wordpress.com/2013/05/image.png"><img alt="image"
  border="0" height="117" src=
  "http://roundcrisis.files.wordpress.com/2013/05/image_thumb.png?w=280&amp;h=117"
  style=
  "background-image:none;padding-top:0;padding-left:0;margin:0 0 0 5px;display:inline;padding-right:0;border-width:0;"
  title="image" width="280"></a></p>

  <p>The diagram above describes the flow of the update thread(red) and
  rendering thread(blue), the hatched squares represent blocking.</p>

  <p>At the initial stage, the render thread will be waiting for the render
  commands to become available, it will be signalled from the update thread.
  Once that happens, the render thread will swap the buffers, signal to the
  update thread that the commands have swapped and that the render thread is
  ready to start drawing and start drawing.</p>

  <p>This signalling process works well also for the situation when the update
  frame takes longer to update and the render thread needs to wait for the
  render commands to become available.</p>

  <p><a href=
  "http://roundcrisis.files.wordpress.com/2013/05/image1.png"><img alt="image"
  border="0" height="157" src=
  "http://roundcrisis.files.wordpress.com/2013/05/image_thumb1.png?w=313&amp;h=157"
  style=
  "background-image:none;padding-top:0;padding-left:0;margin:0 0 0 5px;display:inline;padding-right:0;border-width:0;"
  title="image" width="313"></a></p>

  <p>Finally the situation where rendering takes longer is also covered, as we
  see in the the update thread is waiting until rendering is finished</p>

  <p><a href=
  "http://roundcrisis.files.wordpress.com/2013/05/image3.png"><img alt="image"
  border="0" height="114" src=
  "http://roundcrisis.files.wordpress.com/2013/05/image_thumb3.png?w=288&amp;h=114"
  style=
  "background-image:none;padding-top:0;padding-left:0;margin:0 0 0 5px;display:inline;padding-right:0;border-width:0;"
  title="image" width="288"></a></p>

  <h3>The implementation</h3>

  <p>For the purposes of this example we will be using XNA. To have something
  to show and compare against, I’m starting off with the&nbsp; <a href=
  "http://xbox.create.msdn.com/en-US/education/catalog/sample/primitives_3d"
  target="_blank">3d primitives sample</a> from XNA Creators code club.</p>

  <p>I am going to skip the details about how to draw vertices, there are many
  other blog posts that cover that and focus on the threading and concurrency
  issues.</p>

  <p>So, for a start we need to create the update thread. To that effect we
  will instantiate a class called UpdateLoop in a Task that will simply loop on
  executing Update as follows.</p>

{% highlight c# %}
 Task.Factory.StartNew(() = 
{
        var gl = new UpdateLoop(_renderer);
        gl.Loop();
});
{% endhighlight %}

  <p>The loop in UpdateLoop: (Note: the loop is not time stepped, ie you should
  not use a while(true) like this in production).</p>

{% highlight c# %}
public void Loop()
{
    _stopwatch.Start();
    while (true)
    {
        Update();
    }
}
{% endhighlight %}

  <p>The code for the loop is (i think) pretty self explanatory, when calling
  Update in line 5 it will follow the sequence as described in diagram
  below.</p>

  <p><a href=
  "http://roundcrisis.files.wordpress.com/2013/05/capture12.png"><img alt=
  "Update loop sequence diagram" border="0" height="262" src=
  "http://roundcrisis.files.wordpress.com/2013/05/capture1_thumb2.png?w=283&amp;h=262"
  style=
  "background-image:none;padding-top:0;padding-left:0;margin:0 0 0 5px;display:inline;padding-right:0;border-width:0;"
  title="Update loop sequence diagram" width="283"></a></p>

  <p>It is probably interesting to see what <em>AddCube</em>() looks like :</p>

{% highlight c# %}
public void AddCube(Cube primitive)
{
    var translation = Matrix.CreateFromYawPitchRoll(
                            primitive.Rotation.X, 
                            primitive.Rotation.Y, 
                            primitive.Rotation.Z) *
            Matrix.CreateTranslation(primitive.Position);
 
    _updatingRenderCommands.Add(
        new RenderCommand
                {
                    Color = primitive.Color, 
                    Radius = primitive.Radius, 
                    World = translation
                });
}
{% endhighlight %}

  <p>As you can see from the sequence diagram, after looping on
  <em>renderer.AddCube()</em> there is a call to <em>renderer.EndFrame()</em>,
  here is where we need to signal that the render commands are ready and the
  update thread will be now waiting for the render buffers to be swapped.</p>

 {% highlight c# %}
 public void EndFrame() { 
 	_renderCompleted.WaitOne(); 
 	_renderComandsReady.Set(); 
 	_renderActive.WaitOne(); 
 } 
{% endhighlight %}

  <p>From the render thread point of view, this is what the sequence diagram
  looks like:</p>

  <p><a href=
  "http://roundcrisis.files.wordpress.com/2013/05/capture3.png"><img alt=
  "Draw call sequence diagram" border="0" height="250" src=
  "http://roundcrisis.files.wordpress.com/2013/05/capture_thumb2.png?w=283&amp;h=250"
  style=
  "background-image:none;padding-top:0;padding-left:0;margin:0 0 0 5px;display:inline;padding-right:0;border-width:0;"
  title="Draw call sequence diagram" width="283"></a></p>

  <p>In my game class (the main class that inherits from XNA’s game class) , in
  Draw(), we call _renderer.Draw():</p>

{% highlight c# linenos%}
  public void Draw(GraphicsDevice device, Matrix view, Matrix projection)
{
    _renderActive.Reset();
    _renderCompleted.Set();
    _renderComandsReady.WaitOne();
 
    _renderCompleted.Reset();
    _renderComandsReady.Reset();
    SwapBuffers();
    _renderActive.Set();
 
    _cubePrimitive = _cubePrimitive ?? new CubePrimitive(device);
    foreach (var renderingRenderCommand in _renderingRenderCommands)
    {
        _cubePrimitive.Draw(renderingRenderCommand.World, 
                                    view, 
                                    projection, 
                                    renderingRenderCommand.Color
                                    );
    }
}
{% endhighlight %}

  <p>This is probably the most complex method in the whole example. The
  _renderActive is reset because at this point we want the update thread to
  block when on wait, this was set to wait from <em>_renderer.EndFrame().</em>
  We set _renderCompleted&nbsp; here to unblock the update thread and then we
  wait for _renderCommandsReady to be signalled, effectively putting the
  renderer to sleep until there are more commands to render.</p>

  <p>Before calling SwapBuffers() _renderCompleted is reset so that if the
  update thread reaches the end of a frame, it will sleep until the render
  thread has finished swapping the buffers.</p>

  <p>Immediately after, a call to reset _renderCommandsReady ensures that the
  render thread will go to sleep on the next Draw call until there are some
  commands to render.</p>

  <p>I am not terribly sure the explanation above is clearer than the actual
  code to be honest, but after <span style=
  "text-decoration: line-through">4</span> 6 attempts I’m giving up.</p>

  {% highlight c# linenos %}
  private void SwapBuffers()
{
     
    if (_updatingRenderCommands == _bufferedRenderCommandsA)
    {
        _updatingRenderCommands = _bufferedRenderCommandsB;
        _renderingRenderCommands = _bufferedRenderCommandsA;
 
    }
    else if (_updatingRenderCommands == _bufferedRenderCommandsB)
    {
        _updatingRenderCommands = _bufferedRenderCommandsA;
        _renderingRenderCommands = _bufferedRenderCommandsB;
    }
    _updatingRenderCommands.Clear();
}
{% endhighlight %}
  <p>Finally SwapBuffers(). There’s no synchronization happening here so, we
  are just switching buffers. Before calling this method the
  _renderComandsReady was blocked</p>

  <p>And that is pretty much all, the complete sample is available from
  <a href="https://github.com/Andrea/c4g/tree/master/MutithreadingWithDoubleBufferLockFree"
  target="_blank">github</a> .</p>

  <p>&nbsp;</p>

  <h4><strong>References and interesting related articles</strong></h4>

  <p>Most excellent Quake 3 code review <a href=
  "http://fabiensanglard.net/quake3/index.php">http://fabiensanglard.net/quake3/index.php</a></p>

  <p>Threading your game loop <a href=
  "http://www.altdevblogaday.com/2011/07/03/threading-and-your-game-loop/">http://www.altdevblogaday.com/2011/07/03/threading-and-your-game-loop/</a></p>

  <p>For the craic <a href=
  "http://en.wikipedia.org/wiki/Multiple_buffering">http://en.wikipedia.org/wiki/Multiple_buffering</a></p><br>
