**Made by Nicolò Baroncini (1834907)**

## Research about application(4_RA)
### Do a personal research about the real world window to viewport transformation, and note separately the formulas and code which can be useful for your present and future applications.
Window to Viewport Transformation is the process of transforming 2D world-coordinate objects to device coordinates. Objects inside the world window are mapped to the viewport which is the area on the screen where world coordinates are mapped to be displayed.
In the next figure it's shown this concept.

![image](https://user-images.githubusercontent.com/78324346/138053104-34506e4f-3fed-49d5-a89b-bc358490e7c8.png)

Let's see now some general terms tipically used when talking about world window to viewport transformation:

• ***World Coordinate –*** It is the Cartesian coordinate that we want to represent in the viewport. \
• ***Device Coordinate –*** It is the screen coordinate where the objects are to be displayed, so at any world coordinate is associated a device coordinate. \
• ***Window –*** It is the area on world coordinate selected for display.\
• ***ViewPort –*** It is the area on the device coordinate where graphics is to be displayed.\

It may be possible that the size of the Viewport is much smaller or greater than the Window. In these cases, we have to increase or decrease the size of the Window according to the Viewport and for this, we need some mathematical calculations.
We define:
```
(xբ, yբ) as a point in the World Window
(xᵥ, yᵥ) as the corresponding  point in the associated Viewport
```
We want to calculate the coordinate (xᵥ,yᵥ) and to do so can be followed the procedure below.

![Foglio di brutta-4](https://user-images.githubusercontent.com/78324346/138499181-ad596cd4-0f95-4ad1-bc78-975a99d41d43.jpg)

Let's see now the code useful to our applications.

[1] [https://www.geeksforgeeks.org/window-to-viewport-transformation-in-computer-graphics-with-implementation/](https://www.geeksforgeeks.org/window-to-viewport-transformation-in-computer-graphics-with-implementation/)
