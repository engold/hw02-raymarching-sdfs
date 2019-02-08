# CIS 566 Homework 2: Implicit Surfaces

## Erin Goldberg
pennKey: engold
## References
- Normal Calculation http://jamie-wong.com/2016/07/15/ray-marching-signed-distance-functions/#surface-normals-and-lighting
- SDF Logic from https://www.shadertoy.com/view/llt3R4
- IQ's blog http://www.iquilezles.org/www/articles/distfunctions/distfunctions.htm
- FBM and noise functions from https://thebookofshaders.com/13/
- Lecture Slides on Noise https://docs.google.com/presentation/d/e/2PACX-1vQAK1Xeb7GGqLoDFz_iu9JuXMb-qE9jqKbZDkrXNSybXweqeIn3xvv4LMxetcM9GEugoU0Q0Ft1qUH-/pub?start=false&loop=false&delayms=60000&slide=id.g4cae677c4f_0_852
- Lecture Slides on Implicit Surfaces https://docs.google.com/presentation/d/e/2PACX-1vQYxMlaG9BEf8FiLLu0nOKGuIku2G2FyGAZcKO1tNJy4RriVxR6eDPTTGw9nRbuMJ7wjAvu5szsw-yR/pub?start=false&loop=false&delayms=60000&slide=id.p
- Lecture Slides of Toolbox Functions https://cis700-procedural-graphics.github.io/files/toolbox_functions.pdf
- CIS 560 Ray Casting Slides https://docs.google.com/presentation/d/e/2PACX-1vSNy2AZVsoTFcstvadcN76wLX8vouFxEaWWhz8olaxCDhTFiwt5mJXIkK1hKeIhU6vxrkUoVIod-WYG/pub?start=false&loop=false&delayms=60000&slide=id.g27215b64c6_0_187


## Link to Demo
- When you open the scene, it helps to zoom out a little using the mouse wheel before you do anything else

- Link: https://engold.github.io/hw02-raymarching-sdfs 

![](space1.png)
![](shading.png)
## SDF Raymarched Scene
- I used SDFs to make all of the geometry in the scene, which includes an astronaut, a UFO, and 2 irregularly shaped asteroids.
- I used smoothblend to make the astronaut's suit look continuous. I also used smoothblend for the UFO to make it appear as a single object. The lights are not smoothblended in, but that was an aesthetic choice.
- I used subtraction to create the front asteroid that looks like it has chunks missing, as if it was hit and eroded by floating debris.
- I used Intersection to get a interesting shape for the asteroid in the background.

## Animated Scene Attributes
- Position and rotation for the astronaut and the UFO are animated, as well as the position of the back asteroid and rotation of the front asteroid. The colors of the UFO, astronaut, and asteroids are also animated.

## Toolbox Functions used for Animation
- I used the sawtoothWave function for the jagged, repeated animation of the back asteroid's up and down movement.
- I also used the squareWave function on the back asteroid for the instant movement back and forth for the asteroid's side to side movement.
- Additionally, I used the gain, bias, and smoothstep functions for tweaking the final colors, which was a result of using the mix function for linearly interpolating between two predefined colors based on a function of time. 
![](spacepos.png)
![](spacepos2.png)
![](spacerotate.png)

## Procedural Texturing using toolbox functions and/or noise functions
- I used an FBM and a noise function to get the coloring for the background of my scene. In order to make it look like space, be nebulous, and appear to have depth, I modified the frequency in my implementation to make the final output
look smoother and cloudy-er.  
- I also used the gain and bias functions to increase the contrast of my space background color and make the brighter colors brighter and the darker colors darker.

![](space1.png)

## Shading that involves surface normal computation
- I used the normals to do Lambertian Shading and Blinn Phong shading. Every material has a base lambert color and materials that should be shiny, like the astronaut's mask and boots and the UFO, have a specular highlight on them from Blinn Phong Shading.

![](shading.png)

## GUI Elements
- The user can modify the X, Y, and Z position of the astronaut.
- The user can also modify the speed at which the UFO is rotating.
- The user can also turn on/off both the overall animation and the animation of the colors.

## Issues
- Optimization using BVH
  + I have most of the setup for using bounding boxes arranged in a BVH, but I couldn't get it to work correctly so ultimately it is not being used.


