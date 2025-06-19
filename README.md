# OpenGL-Rendering

|     Task     |   Description   |
|:------------:|:---------------:|
| Frustum Manipulation | Changed camera perspective, increased triangle count, and adjusted clipping to better visualise the frustum. |
| Rotation Matrix   | Applied x-axis rotation using `mat_motion` with `Math.PI/2`, changing object orientation.  |
| Phong Shading             | Implemented Phong lighting model to calculate realistic specular highlights. |
| Blinn - Phong Reflection             |  Replaced Phong reflection with Blinn-Phong using a halfway vector to compute specular highlights. |
| Per-Vertex vs Per Fragment (Gouraud Shading)   | Implemented per-vertex (Gouraud) shading, resulting in visible interpolation artifacts compared to per-fragment shading. |
| Points vs Lines Primitives | Switched triangle rendering to points and lines by changing `gl.drawElements` mode, showing different primitive representations. |
| Fragment Z Coordinate Shading           | Used `gl_FragCoord.z` to map fragment depth into grayscale, visualising depth variation across the surface. |
| Adding Random Noise to Vertices      |                |
| Mapping Texture to Model       |                |
| Bilinear/Mipmap Blurring      |                |





## Frustrum Manipulation
In this task, the camera perspective was changed by adjusting the `eye` vector, and the number of triangles was increased to 1000. Additionally, rendering of the triangles was removed to clearly expose the shape and boundaries of the frustum. These changes allow for a more accurate and detailed visualisation of the viewing volume, as seen in the three output canvases.

<img src="Images/Lab2/L2B/B5.png" alt="Description" width="300">

## Rotation Matrix 
Created a rotation matrix using `mat_motion`, where the object was rotated on the x-axis using an angle of `Math.PI/2` (90 degrees). This changed the view through continuous theta increments, resulting in different object orientations as visualised in the screenshots.

<p float="left">
  <img src="Images/Lab3/L3A/A1i.png" alt="Description" width="300"/>
  <img src="Images/Lab3/L3A/A1ii.png" alt="Description" width="300"/>
</p>


## Phong Shading
In this task, I implemented the Phong reflectance model by calculating the specular term using the surface normal, light direction, and reflection vector. This enhanced the lighting by adding realistic specular highlights, based on material properties and light positioning.

<p float="left">
  <img src="Images/Lab3/L3B/B1i.png" alt="Description" width="300"/>
  <img src="Images/Lab3/L3B/B1ii.png" alt="Description" width="300"/>
</p>

## Blinn - Phong Reflection
For this task, I modified the existing Phong shading algorithm by implementing the Blinn-Phong reflection model. This involved calculating a new halfway vector `h` using the sum of the light and view directions. The specular component was then computed using this vector, avoiding the need to calculate the reflection vector `r`. This approach changes how highlights appear and can be more efficient. The updated calculation is shown in the code snippet and reflected in the output render.

<p float="left">
  <img src="Images/Lab3/L3B/B3i.png" alt="Description" width="300"/>
  <img src="Images/Lab3/L3B/B3ii.png" alt="Description" width="300"/>
</p>

##  Per-Vertex vs Per Fragment (Gouraud Shading) 

<p float="left">
  <img src="Images/Lab3/L3B/B4i.png" alt="Description" width="300"/>
  <img src="Images/Lab3/L3B/B4ii.png" alt="Description" width="300"/>
</p>

## Points vs Lines Primitives
In this task, I explored different primitive types by modifying the parameters of the `gl.drawElements` function. I replaced triangle rendering with `gl.POINTS` and adjusted `gl_PointSize` to visualize individual vertices on the mesh. For the second variation, I used `gl.LINES` instead, which connected vertices and emphasized the edges. This allowed for direct comparison between dot-based and edge-based representations of the mesh geometry.

<p float="left">
  <img src="Images/Lab3/L3C/C1i.png" alt="Description" width="300"/>
   <img src="Images/Lab3/L3C/C1ii.png" alt="Description" width="300"/>
</p>

## Fragment Z Coordinate Shading
In this task, I accessed the fragment's depth value using `gl_FragCoord.z` and applied a linear transformation to normalize it to a 0–1 range. I inverted the result to better highlight depth differences and passed this normalized value to all RGB channels in `gl_FragColor`, producing a grayscale depth visualization. The result appears smoother than previous outputs, likely due to using triangles instead of points or lines, which ensures more continuous interpolation between fragments.

<p float="left">
  <img src="Images/Lab3/L3C/C2.png" alt="Description" width="300"/>
</p>

