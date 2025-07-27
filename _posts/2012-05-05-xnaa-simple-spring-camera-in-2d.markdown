---
author: roundcrisis
comments: true
date: 2012-05-05 14:10:29+00:00
layout: single
classes: wide
slug: xnaa-simple-spring-camera-in-2d
title: XNA - A Simple Spring Camera in 2D
wordpress_id: 990
tags:
- acceleration force mass
- programming
---

Cameras are cool, so lets keep at it and try a spring camera, i.e. one that follows you around.

The initial aspect of the camera and how to use it is on the [previous post](http://roundcrisis.com/2012/04/19/xna-a-simple-2d-camera/) on cameras, so I ll let you go and have a look there.

The spring camera is very similar to a simple camera, but with Hooke's Law applied. Hooke's Law states that the extension of a helical spring is directly proportional to the weight applied, provided the elastic limit of the spring is not exceeded. I read this a few times and couldnt figure how to turn this into code , so I went to Khan Academy and found this [video](http://www.youtube.com/watch?feature=player_embedded&v=ZzwuHS9ldbY#!), where the formula **F = –k x** is explained.

[youtube=http://www.youtube.com/watch?feature=player_embedded&v=ZzwuHS9ldbY]

If we use the formula as is, then the spring would be “springing” forever, so when calculating the force we will use some damping. So the new update method in Camera.cs now looks like this







    
    <span style="color:#606060;" id="lnum1"> 1:</span> <span style="color:#0000ff;">public</span> <span style="color:#0000ff;">void</span> Update(<span style="color:#0000ff;">float</span> elapsedSeconds, <span style="color:#0000ff;">float</span> rotation, Vector2 desiredPosition, <span style="color:#0000ff;">float</span> zoom)




    
    <span style="color:#606060;" id="lnum2"> 2:</span>     {




    
    <span style="color:#606060;" id="lnum3"> 3:</span>         var delta = _position - desiredPosition;




    
    <span style="color:#606060;" id="lnum4"> 4:</span>         var force = -SpringStiffness * delta - Damping * _velocity;




    
    <span style="color:#606060;" id="lnum5"> 5:</span>




    
    <span style="color:#606060;" id="lnum6"> 6:</span>         var acceleration = force / Mass;




    
    <span style="color:#606060;" id="lnum7"> 7:</span>         _velocity += acceleration * elapsedSeconds;




    
    <span style="color:#606060;" id="lnum8"> 8:</span>         _position += _velocity * elapsedSeconds;




    
    <span style="color:#606060;" id="lnum9"> 9:</span>




    
    <span style="color:#606060;" id="lnum10"> 10:</span>         Transform = Matrix.CreateTranslation(-_position.X, -_position.Y, 0) *




    
    <span style="color:#606060;" id="lnum11"> 11:</span>                     Matrix.CreateRotationZ(rotation) *




    
    <span style="color:#606060;" id="lnum12"> 12:</span>                     Matrix.CreateScale(zoom, zoom, 1)*




    
    <span style="color:#606060;" id="lnum13"> 13:</span>                     Matrix.CreateTranslation(_halfScreenSize.X, _halfScreenSize.Y, 0);




    
    <span style="color:#606060;" id="lnum14"> 14:</span>     }










The line

var force = -SpringStiffness * delta - Damping * _velocity;

Is respecting the formula F= –kx, where k is the SpringStiffness and x is the delta(in orange). The second part of this assignment(in green)  is applying some damping proportional to the velocity.

Once we have the result of calculating the force, we use the force vector to calculate the acceleration that, in turn that value is used to calculate the velocity and position.

Finally, once we have the position, the matrix transformation is calculated in the same way we calculated this for the simple camera ([in previous post](http://roundcrisis.com/2012/04/19/xna-a-simple-2d-camera/)).

You can get a complete working sample [here](https://github.com/Andrea/SpringCamera2dXNA).
