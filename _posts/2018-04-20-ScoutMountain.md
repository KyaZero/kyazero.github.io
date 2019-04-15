---
layout: post
description: 2D Platformer
onhome: false
title: Scout Mountain
project: true
---
## Trailer
<style>.embed-container { position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%; } .embed-container iframe, .embed-container object, .embed-container embed { position: absolute; top: 0; left: 0; width: 100%; height: 100%; }</style><div class='embed-container'><iframe src='https://www.youtube.com/embed/oSd9YIrzHpo' frameborder='0' allowfullscreen></iframe></div>

## Project Details
- 2D Top down adventure game
- 8 weeks half-time
- Made with an our house 2D C++ engine

## Contributions
- **Player** - I wrote the player and tweaked all the metrics to match our reference game Celeste.
- **Rendering** - I wrapped our sprite class and set up a renderer to handle all the separate shaders and layers that sprites would be in.
- **Camera** - I wrote the camera and frustum culling we used for tiles.
- **Particle System** - I wrote a particle system based on [Löve2D](https://love2d.org/)'s interface with support for hot-loading and many tweakable parameters such as radial acceleration and tangential velocity.
- **Post Processing** - I implemented a shockwave shader effect when dashing, and also added several post processing effects such as chromatic aberration and a grayscale filter

## Screenshots
![](../assets/img/ScoutMountain_Screenshot_01.png)
![](../assets/img/ScoutMountain_Screenshot_02.png)
![](../assets/img/ScoutMountain_Screenshot_03.png)
![](../assets/img/ScoutMountain_Screenshot_04.png)
![](../assets/img/ScoutMountain_Screenshot_05.png)