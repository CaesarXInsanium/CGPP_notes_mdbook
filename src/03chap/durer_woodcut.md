# Durer Woodcut

- Woodcut is a machine that allows for easy drawing ob objects using a string, two people
```
*Input*: scene containing objectss, location of eye point
 *Ouput*: drawing of objects
 init drawing to be blank
 for each object o:
  foreach visible point P of O:
    open shutter
    place pointer at P
    if string from P to eyue-point touch boundary of frame
      do nothing
    else
      hold pencil at point where string passes trought the frame
      hold string aside
      close shutter to make mancil mark on paper
```

- here we draw a limited number of points in order to be able to draw something using computationally cheap methods
- avoid drawing points outside of range of view

for every world coordinate there is a perpective projections unto a 2d plane sucht that the x' is x / z

$$
x' = x/z
$$

`Normalized Device Coordinates`: describe fraction of the left-to-right or top-to-bottom range of device.

`Normalization`: converting numbers in range x_min to x_max to range (0,1)

`Vanishing Point`: when lines that are parallel in world appear to converge in rendering picture

`Projective Geometry`: study of projections and transformations of space

`View Volume`: section in world space that will be visible when rendered
