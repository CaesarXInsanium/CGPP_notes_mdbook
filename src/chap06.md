# Introduction to Fixed-Function 3D Graphics and Hierarchical Modeling

- there are a variety of different purposes for graphics and 3d graphics at variety of different levels of accuracy and realism
- WPF is retained mode while things like OpenGL are immediate mode, at least that is what it says on the thing

## Approximation the Physics of Interaction of Light with objects

`Fixed-Function Pipeline`: uses triangles and simple shading rules in order to try as best as possible to get the users to see what the developer wants them to see
Often times software based. OpenGL 1.0 and Direct3D are the precursors to modern graphics APIs

- many of the algorithms uses in modern computer graphics denote an approximation to something that is accurate and or realistic
- games try to get frames as fast as possible while movies get frames as best looking as possible regardless of rendering time
- many of the approximation algorithms today were developed in the early days of computer graphics when computing resources were limited
- fixed function APIs are good for getting an understanding but not good for making practica, quality and/or real-time applications

## High-Level Overview of WPF 3D

not very important. I'm going to focus on interesting concepts

`World Coordinate System`: abstract application coordinate system whose unit of measurement open to interpretation by developer as to meaning of a single unit

`View Volume`: box or pyramid that denotes all rendered objects

- configuration of 3D scene requires geometric objects, materials, their transforms, camera position, projection matrix, shaders?

## Introduction Mesh and Lighting

- `Clipping Planes`: planes that are used in order to cut away vertices and geometry that should be rendered, in particular thing that are too close
to camera or that are two far away
- `Point Light`: single point from which light in all directions equally
- `Directinal Light`: point light that is very far away and as such the light rays all seem to be going in same exact direction


- when denoting a face, order the vertices in counterclockwise order from point of view of someone looking at the correct face
- true color or gradient of object is determined by the normal of the surface of ab object

## Lighting vs Shading

- `Flat/Constant Shading`: one vertex is selected for each triangle. That is used in order to compute light and shading. Overall the entire triangle will have the same color, making the object in question triangular in appearance. 
- `Interpolated Shading`: method for shading that takes the normal of a vertex. Can also be interpolated with other vertex in order to have a proper gradient of shading colors
- `Vertex normal`: vector that is perpindicular to surface and point in general direction from which a viewer can see a surface

## Surface Texture

- `Texture Mapping`: wrapping 3D surface with 2D image. can be used to calculate many things most notabality the image that is represented on a vertex of the 'skin' of an object, if that makes sense. Each vertex on 3D object corresponds to a point on the texture map and as such can also interpolate the in-between values
- `Tiling Texturing`: when end of 2D image is reached the same image just repeats, either via mirror or not
- `Stretching`: using sufficiently high resolution textures, large images can be rendered in order to substiture complex of large models such as skies or cities

## WPF Reflectance

- `light`: can mean spectral distribution of light wavelenghts, amount of light in each wavelenght, perceptual sensation.
- `attenuation`: amount of light hitting objectg is determined by the distance from the light source and angle of the surface
- `Spot light`: light restricted to travel inside of a single cone
- `Phong Reflectance`: materials are describe using three components of reflection: ambient, diffusion, and specular. 
- `Ambient`: light inherent to all objects in scene.
- `Diffuse`: viwer indedpendent light spewing in all directions
- `Specular`: how glossy and reflective a light source is
- `Reflection Efficiency`: how much of each component a material is capable of reflecting
- `Wise Modeling Principle`: failure since light and colors are describe as 3 numbers RGB and A for alpha.
- `Emmisive Lighting`: allows for reflection of light that ios not actually present externally, something like the sky or a cityscape background
-

Compute intensity if Red Light

$$
I_R = (I_{a,R}, k_{a,R},C_{d,R}) +
\sum_{\text{directional lights} }(I_{dir,R}, k_{d,R},C_{d,R}, (\cos(\theta))) +
\sum_{\text{geometric lights} }(F_{att}I_{geo,R}, k_{d,R}, C_{d,R},(\cos(\theta))) +
\sum_{\text{directional lights} }(I_{dir,R}, k_{s,R}, C_{s,R},(\cos(\phi)^s)) +
\sum_{\text{geometric lights} }(F_{att}I_{geo,R}, k_{s,R}, C_{s,R},(\cos(\phi)^s)) +
$$

- potential for the summation accross all if the light to be greater than one is possible, in order to circumvent this, max of red values if capped to 1.0 or 100%
- specular reflection can have the color affected by both the light color and the material color. Shiny materials reflect more of incoming light
- perfect mirror has 100% reflection effieciency at all points except when viewpoint is directly on **r**

## Scene Modeling using Scene Graph

- `Scene Graph`: hierarchical organization and description of meshes, materials that describe a scene.
- `Subcomponents`: dividing parts of model into smaller parts for a variety of different reasons such as different materials for diofferent sections, position, rotation, colors. Such as the legs limbs of the model if a robot, instationation can be done to reuse same mesh, 
- `Pick correlation`: identification of which part of model is being clicked on 
- `instance transform`: used to position, resize and rotate component into position 
- `joint transform`: used to simulate movement of joint during animation. starting from the space of individial component, do translate to correct position for rotate transform, with the correct axis rotate to appropiate joint rotation. move back to model space and then translate over to complete model space
- `object coordinat system`: abstract coordinate system used to denote positions of vertices in model in regards to origin for single model. typically center of model is the origin

- Top Piece scene,
  - model
    - limb
      - leg
        - knee
      - arm
    - head
      - neck
  - sky
  -
