# Ray Casting and Rasterization

Note: this section will mostly be done in seperate git repo

- `RayCasting`: method of rendering done by shooting rays from each pixel and seeing what gets hit.
- `Rasterization`: method of rendering where triangles are projected unto a 2D surface and we try and figure out which pixels fit in each pixel

- all of rendering is integration. The summation across all possible light that can reach a pixel. Computers cannot compute trillions of photons so approximations will have to do instead
- use of software development best practices is recommended
-

## High Level Design Overview

### Scattering

- light that enters the camera are intersection of scene of rays the symbolize light
- pinhole camera is used with a virtual plane that represents film. There is also instant exposure for no blur
- each section in film represnts physical pixels
- coordinate frame has origin at center of virtual plane and camera is looking down negative z-axis
- consider all possible light from all the sources
- for each pixel take the sum of the color of the impacted surface plus contribution from all lights that can hit the thing

### Visible Points

- `Surface`: interface between volumes with homogenous physical properties
- `Lambertian Scattering`: light scattering equally in all directions

- objects are represented using meshes
- meshes represented using triangles
- visible triangles have vertices listed in counterclockwise order from point of view of camera
- to determine visibility of triangle,, determine potential visible points and determine which one are inside of a triangle

### Ray casting: Pixels First

```python
for pixel in canvas:
  ray = ray_from(pixel.pos, camera.pos)
  for triangle in mesh:
    p = intersection(triangle, ray)
    sum = 0
    for d in directions_possible:
      sum += compute_light(lights, d)
    pixel.change_to_highest_x_buffer()
```

- creates one ray for each pixel and casts it
- can be expanded to cast rays recursively

### Rasterization: Triangles First

- images are stored in row-major order, element corresponding to **(x,y)** stored in *(x+y * width)*
- is faster than ray casting because of much lower memory requirements
- 

## Implmentation Platform



