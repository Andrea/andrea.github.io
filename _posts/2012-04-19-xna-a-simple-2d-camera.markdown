---
author: roundcrisis
comments: true
date: 2012-04-19 15:21:10+00:00
layout: single
classes: wide
slug: xna-a-simple-2d-camera
title: XNA - A Simple 2D Camera
wordpress_id: 962
categories:
- gamedev
- xna
tags:
- 2d
- camera
- gamedev
- xna
---

What is a camera? Intuitively we know what a camera is:  simply a way to show the action.

A Camera allows us to deal with the display of the action in a detached way from the action.

Implementation

I like to start with what we are trying to achieve. For the purposes of this post, I want to have two cameras showing the same action at different zoom levels, like this:

[![Capture](http://roundcrisis.files.wordpress.com/2012/04/capture_thumb.png)](http://roundcrisis.files.wordpress.com/2012/04/capture.png)

In this case we want 2 cameras, with each camera having it’s own ViewPort that we assign when creating like this:

    
    <span class="kwrd">int</span> halfScreenWidth = GraphicsDevice.Viewport.Width/2;
    _camera1 = <span class="kwrd">new</span> Camera(<span class="kwrd">new</span> Viewport(0, 0, halfScreenWidth - 3, GraphicsDevice.Viewport.Height));


What we are saying with that is that the Camera class will have a Viewport that occupies the left side of the screen.  The - 3 is there to add a visible gap between the left and right sides of the screen. Lets look at the following portion of the Draw method. Please note you could have all the parameters for _spriteBatch.Begin() null, except for the transform.




    
    <span class="lnum"> 1: </span>            GraphicsDevice.Viewport = _camera1.Viewport;
    <span class="lnum"> 2: </span>



    
    <span class="lnum"> 3: </span>            _spriteBatch.Begin(SpriteSortMode.Deferred, BlendState.AlphaBlend, SamplerState.PointClamp, DepthStencilState.None, RasterizerState.CullNone, <span class="kwrd">null</span>, _camera1.Transform);
    <span class="lnum"> 4: </span>            _level.Draw(_spriteBatch);



    
    <span class="lnum"> 5: </span>            _spriteBatch.Draw(_tankTexture, _tankPosition, <span class="kwrd">null</span>, Color.White, _rotation, <span class="kwrd">new</span> Vector2(_tankTexture.Width / 2, _tankTexture.Height / 2), 1, SpriteEffects.None, 0);
    <span class="lnum"> 6: </span>            _spriteBatch.End();





Since we have a viewport  per camera, the graphics device needs to know which one to use, and that’s what we are doing in line 1 in the code above. The other important part of the code is the last parameter of the _spriteBatch.Begin call, where we are using the transformation matrix from the camera. This transform is calculated on each update.

So finally lets look at the Camera class:




    
    <span class="lnum"> 1: </span>    <span class="kwrd">public</span> <span class="kwrd">class</span> Camera









    
    <span class="lnum"> 2: </span>    {









    
    <span class="lnum"> 3: </span>        <span class="kwrd">public</span> Matrix Transform { get; <span class="kwrd">private</span> set; }









    
    <span class="lnum"> 4: </span>        <span class="kwrd">public</span> Viewport Viewport { get; <span class="kwrd">private</span> set; }









    
    <span class="lnum"> 5: </span>









    
    <span class="lnum"> 6: </span>        <span class="kwrd">public</span> Camera(Viewport viewport)









    
    <span class="lnum"> 7: </span>        {









    
    <span class="lnum"> 8: </span>            Transform = Matrix.Identity;









    
    <span class="lnum"> 9: </span>            Viewport = viewport;









    
    <span class="lnum"> 10: </span>        }









    
    <span class="lnum"> 11: </span>









    
    <span class="lnum"> 12: </span>        <span class="kwrd">public</span> <span class="kwrd">void</span> Update(GameTime gameTime, <span class="kwrd">float</span> rotation, Vector2 position, <span class="kwrd">float</span> zoom)









    
    <span class="lnum"> 13: </span>        {









    
    <span class="lnum"> 14: </span>            Transform = Matrix.CreateTranslation(-position.X, -position.Y, 0) *









    
    <span class="lnum"> 15: </span>                        Matrix.CreateRotationZ(rotation) *









    
    <span class="lnum"> 16: </span>                        Matrix.CreateScale(<span class="kwrd">new</span> Vector3(zoom, zoom, 1)) *









    
    <span class="lnum"> 17: </span>                        Matrix.CreateTranslation(Viewport.Width / 2, Viewport.Height / 2, 0);









    
    <span class="lnum"> 18: </span>        }









    
    <span class="lnum"> 19: </span>    }





The least obvious part of this code lies in the matrix transformation. It is important to understand that we have two coordinate systems in place, the screen and the world. With the transformation matrix we are trying to project the world coordinate system onto the screen system. With that in mind, the first translation matrix (line 14 in the code above) will reposition the world so that point (position.X, position.Y) lines up with the screen's origin. The result is as follows:

[![Capture](http://roundcrisis.files.wordpress.com/2012/04/capture_thumb1.png)](http://roundcrisis.files.wordpress.com/2012/04/capture1.png)[![Capture](http://roundcrisis.files.wordpress.com/2012/04/capture_thumb2.png)](http://roundcrisis.files.wordpress.com/2012/04/capture2.png)

What you see at the top left of the pic is a quarter of the tank. If you change the tank’s position then you will see that the tank remains static at the top left (tho rotation applies) and the world moves underneath it.

[![Capture](http://roundcrisis.files.wordpress.com/2012/04/capture_thumb3.png)](http://roundcrisis.files.wordpress.com/2012/04/capture3.png)

The next line, Matrix.CreateRotationZ, creates a matrix representing a rotation around the Z axis. The Z axis points straight out of the screen. In 2D, to perform a rotation, we always rotate around Z.

[![Capture](http://roundcrisis.files.wordpress.com/2012/04/capture_thumb4.png)](http://roundcrisis.files.wordpress.com/2012/04/capture4.png)

Then we need to scale, using the parameters that we sent on update. Don’t forget we set different levels of zoom in each of the two cameras. We use the overload of Matrix.CreateScale() that takes a Vector3 to create a scaling matrix. However we could use the overload that just takes a float and pass the zoom value as a parameter with the same result. Unsurprisingly applying the scale, scales ![Smile](http://roundcrisis.files.wordpress.com/2012/04/wlemoticon-smile.png).

Finally we want to center the tank in the middle of each viewport and that’s why you apply the last line (line 17 on the sample above).

[![Capture](http://roundcrisis.files.wordpress.com/2012/04/capture_thumb5.png)](http://roundcrisis.files.wordpress.com/2012/04/capture5.png)

And we are done ![Smile](http://roundcrisis.files.wordpress.com/2012/04/wlemoticon-smile.png) tho I'm sure there are plenty of ways to improve the code, but hopefully it will help as a simple example.

If you want to have a better look at the code, a working sample is available [here](https://github.com/Andrea/Simple-2D-camera-Sample). If you have any comments, improvements, questions, as always you are very welcome.

**UPDATE: **I followed up with a post about Spring Camera [here](http://roundcrisis.com/2012/05/05/xnaa-simple-spring-camera-in-2d/).


### Other XNA 2d Camera posts


[XNA Camera 2d with zoom and rotation](http://www.david-amador.com/2009/10/xna-camera-2d-with-zoom-and-rotation/)

Another one that I read after implementation [Terrain, Weather, and more!](http://pwnageincblog.blogspot.com/2012/02/terrain-weather-and-more.html)
