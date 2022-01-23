# Overview of Graphics Pipeline

`Application Model`: data represented by the screen window and shown to user

`Window Manager`: software that manages space allocated for window on screen. Wether or not it is shown.

`Window Chrome`: bars around the window

- graphics application contain UI generator and scene generator. Data is passed to graphics platform which is DirectX in Windows

`Viewport`: area used by graphics API to display the scene

- it is job of application to take internal model of UI and translated into geometric data to send to the rendering system

## GUI Platforms

described how data flows in GUI platforms

1. Layout managers
  1. WPF - Windows
  2. Cocoa - MacOS
  3. Swing
2. Templates
3. Floating Point Coordinates
4. Integer Pixel Coordinates
