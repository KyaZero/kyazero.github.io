---
layout: post
img: Potential_Screenshot_01.png
description: First-Person Shooter
onhome: true
project: true
---
## Trailer
<style>.embed-container { position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%; } .embed-container iframe, .embed-container object, .embed-container embed { position: absolute; top: 0; left: 0; width: 100%; height: 100%; }</style><div class='embed-container'><iframe src='https://www.youtube.com/embed/KlodMg0cQ_A' frameborder='0' allowfullscreen></iframe></div>

## Project Details
- 3D First-Person Shooter
- 10 weeks half-time
- Made with our own C++ DirectX11 engine

## Contributions
- **Screen Space Reflections** [read more](/SSR/)
- **Volumetric Lighting** - I based my implementation on [this](http://www.alexandre-pestana.com/volumetric-lights/) post, and tweaked it so that it would look and work like we wanted it to for this game.
- **Area Lights** - I implemented rectangular, tube and sphere area lights for this game.
- **More Powerful Particle System** - I remade our particle system as our artists felt they wanted a bit more control with their effects compared to the old particle system.
- **Game feel** - I worked quite a bit with game feel, things such as the gun's emissive increasing when you shoot and healthbars having nice easings etc.
- **Material system improvements** - I allowed for artists to configure custom data that they could send as a constant buffer to the shaders, allowing for cool vertex animations and such.
- **First person camera** - I wrote the camera, used raw input to make it more responsive and tweaked the camera shake from the last [project](/Spite/).

## Screenshots
---
![](../assets/img/Potential_Screenshot_01.png)