# Evolution of 2D Graphics Platforms

contains mostly history. Will only jot down important ideas

`Primitives`: simple geometric shapes that can be drawn

- drawing images based on integer coordinate systems of pixel was a bad idea because they mapped differently in accordance to the different DPIs and resolutions of different displays
- switched to floating point representations of coordinate systems. Being from -1 to 1. Allowed another level of abstraction

`Immediate Mode`: allows thing and efficient access to graphics output device. Direct CPU manipulation of vertex data. Or more control given to application dev

`Retained Mode`: 

`Scene Graph`: data structure detailing the data for rendering the scene on a variety of platforms

`Precedural Code`: code for interfacing the graphics API.

`Declarative Specification`: expressed in markup language.

## Layers to WPF application specification

- Object oriented API: classes providing WPF functionality
- XMAL: used to declare large amount of UI design
- Tools: Graphics API's, libraries and such

`Abstract Coordinate System`: coordinate system that is open to interpretation on the length of one unit
