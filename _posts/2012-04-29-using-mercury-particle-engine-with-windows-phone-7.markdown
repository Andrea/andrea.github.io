---
author: roundcrisis
comments: true
date: 2012-04-29 17:46:18+00:00
layout: single
classes: wide
slug: using-mercury-particle-engine-with-windows-phone-7
title: Using Mercury Particle Engine with Windows Phone 7
wordpress_id: 984
categories:
- gamedev
- xna
tags:
- gamedev
- mercury
- particle
- particle engine
- xna
---

This a very simple walk through to use Mercury on a Windows Phone 7 project.


### Get the binaries


As far as I can see, Mercury supports Windows Phone 7 only in version 4.0, if you go to the project page you _**wont** _find this on downloads, as it's not yet released.

[![Capture](http://roundcrisis.files.wordpress.com/2012/04/capture6.png)](http://mpe.codeplex.com/releases)

So, you have to get the sources from [here](http://mpe.codeplex.com/SourceControl/list/changesets) and build the project and find the correct binaries. An alternative is to download them from [here](https://github.com/downloads/Andrea/MercuryParticleEngine/Mercury.4.0_WindowsPhone.zip) (I forked the repo and added the binary download for WP7 ) If you ask nicely I’ll add all the other binaries.

Once you have the binaries, include ProjectMercury.dll in the project where you want to use the particle engine, and add ProjectMercury.ContentPipeline.dll to the content project.


### Code


I am not entirely sure where is the best place for the initialization code, you can probably place it in LoadContent, tho I did create the new instance of SpriteBatchRenderer in the constructor of my game class.







    
    <span style="color:#606060;" id="lnum1"> 1:</span> <span style="color:#008000;">// It needs the GraphicsDeviceManager</span>




    
    <span style="color:#606060;" id="lnum2"> 2:</span> _spriteBatchRenderer = <span style="color:#0000ff;">new</span> SpriteBatchRenderer{ GraphicsDeviceService = _graphics };




    
    <span style="color:#606060;" id="lnum3"> 3:</span>




    
    <span style="color:#606060;" id="lnum4"> 4:</span> _particleEffect = Content.Load<ParticleEffect>(<span style="color:#006080;">"Demo1"</span>);




    
    <span style="color:#606060;" id="lnum5"> 5:</span>




    
    <span style="color:#606060;" id="lnum6"> 6:</span>             <span style="color:#0000ff;">foreach</span> (var emitter <span style="color:#0000ff;">in</span> _particleEffect.Emitters)




    
    <span style="color:#606060;" id="lnum7"> 7:</span>             {




    
    <span style="color:#606060;" id="lnum8"> 8:</span>                 emitter.ParticleTexture = Content.Load<Texture2D>(<span style="color:#006080;">"Star"</span>);




    
    <span style="color:#606060;" id="lnum9"> 9:</span>                 emitter.Initialise();




    
    <span style="color:#606060;" id="lnum10"> 10:</span>             }




    
    <span style="color:#606060;" id="lnum11"> 11:</span>             _spriteBatchRenderer.LoadContent(Content);










All you are doing is loading the particle effect through the content pipeline. Then you are iterating over the emitters in the effect to assign the ParticleTexture value, ie a texture you just loaded, and initializing each of the emitters. Finally you need to call LoadContent, calling this method is required because it creates the internal SpriteBatch instance* .

In the update you will need to call







    
    <span style="color:#606060;" id="lnum1"> 1:</span> <span style="color:#008000;">//position is a Vector3</span>




    
    <span style="color:#606060;" id="lnum2"> 2:</span> _particleEffect.Trigger(<span style="color:#0000ff;">ref</span> position);




    
    <span style="color:#606060;" id="lnum3"> 3:</span> _particleEffect.Update((<span style="color:#0000ff;">float</span>) gameTime.ElapsedGameTime.TotalSeconds);










You need to Trigger the particle with a position (there are a number of overloads for this method, make sure you check this out) and then Update. If you fail to do either of those calls, no particles will be rendered.

Finally in the Draw function:







    
    <span style="color:#606060;" id="lnum1"> 1:</span> var matrix = Matrix.Identity;




    
    <span style="color:#606060;" id="lnum2"> 2:</span> var cameraPosition = Vector3.Zero;




    
    <span style="color:#606060;" id="lnum3"> 3:</span> _spriteBatchRenderer.Transformation = Matrix.Identity;




    
    <span style="color:#606060;" id="lnum4"> 4:</span> _spriteBatchRenderer.RenderEffect(_particleEffect, <span style="color:#0000ff;">ref</span> matrix, <span style="color:#0000ff;">ref</span> matrix, <span style="color:#0000ff;">ref</span> matrix, <span style="color:#0000ff;">ref</span> cameraPosition);










Please find a full working sample [here](https://github.com/Andrea/MercuryParticleEngineWP7Sample)

And this would be what you see when you run the project ![Smile](http://roundcrisis.files.wordpress.com/2012/04/wlemoticon-smile1.png)

[![Capture](http://roundcrisis.files.wordpress.com/2012/04/capture_thumb6.png)](http://roundcrisis.files.wordpress.com/2012/04/capture7.png)


### Some thoughts


I have to admit, I find it strange that  the constructor for SpriteBatchRenderer doesn't require GraphicsDeviceManager, and instead you need to initialize the property, if you  don't set this property before you call LoadContent, then you get a  NullReferenceException, as this is where the internal instance of SpriteBatch  is created and a GraphicsDevice is required.

My suggestion here would be to have two versions of the constructors, one where you pass the reference of spriteBatch you have, and another one where you pass the instance of GraphicsDevice, as all usages point to only actually consuming that.

These are just some thoughts on the API, and there might be really good reasons for the decisions made this way that I don't know about. I think that all in all this is a great project, thanks to the creators and maintainers of it.
