# Computer Graphics final project
OpenGL game engine made in C++.

## Features:
- Compatible with OpenGL 3.3 and above 
- Phong illumination model implemented glsl shaders
- Built in terrain generator with Perlin noise and hydraulic erosion
- Terrain textures applied automatically depending on the height and slope of the terrain.
- Emissive, normal, specular and diffuse textures
- Transparent objects

## Description 

For this project i implemented a fully functional terrain generator, using Perlin noise and hydraulic erosion.
I also added an helicopter 3d model (.obj) and unwrapped the UV with Blender to create a UV map and apply the textures.

To ensure the modularity of the code, I divided its functionality into classes, following the principles of object-oriented programming. For example, the Terrain class encapsulates all the attributes of a terrain and the functions that allow you to work with it. Besides, the Model class works with the generation, loading and updating of models, so that, after creating the terrain data with the Terrain class, we can generate it's model with the Model class.  

The terrain code allows you to modify all kinds of variables to get different results. The code is extensively commented so you can easily understand what it does.

To render the terrain, I have used a combination of colors and textures as if we were using a splatmap together with a colormap but generated dynamically:

- The textures are applied depending on the height and slope of the terrain.
- There are three colors that are mixed with the textures to homogenize three areas of the terrain:

  - Snow: white color. It is applied with a higher degree of intensity.
  - Vegetation: green color.
  - Rock: grayish brown color.
  
Two textures have been used for the terrain: one for the vegetation zones and another for the rocky/snowy zones. For the vegetation zones a grass texture with removed shadows (albedo), a normal map and a specular map have been used. For the rocky areas the same has been done, but with a rock texture.

You can enable mesh rendering of scene elements with the 'w' key..

The terrain incorporates hydraulic erosion simulation functionality. Pressing the 'e' key simulates the erosion generated by the fall of 1000 water drops on random points of the terrain (the erosion parameters are fully customizable to achieve different results). After finishing the process, the terrain is rendered with the erosion applied.
You can adjust the coloring/texturing of different zones of the terrain (vegetation, rocks, snow) with the t/T key.

*It's my first project with OpenGL and C++ so the code may have bugs and not be optimal. Use it at your own risk.

## Credits

❤️ Special thanks to Nick for inspiring me with his article: https://weigert.vsos.ethz.ch/2020/04/10/simple-particle-based-hydraulic-erosion/

The hydraulic erosion algorithm coded in this project is an optimized version
of the algorithm created by him: https://github.com/weigert/SimpleErosion

## License

MIT license





