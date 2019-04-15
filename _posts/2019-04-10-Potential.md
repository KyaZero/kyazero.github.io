---
layout: post
img: Potential_Screenshot_01.png
description: First-Person Shooter
onhome: true
project: true
---
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