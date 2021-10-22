**Made by Nicolò Baroncini (1834907)**

## Research about application(4_RA)
### Do a personal research about the real world window to viewport transformation, and note separately the formulas and code which can be useful for your present and future applications.
Window to Viewport Transformation is the process of transforming 2D world-coordinate objects to device coordinates. Objects inside the world window are mapped to the viewport which is the area on the screen where world coordinates are displayed.
In the next figure is shown this concept.

![image](https://user-images.githubusercontent.com/78324346/138053104-34506e4f-3fed-49d5-a89b-bc358490e7c8.png)

Let's see now some general terms tipically used when talking about world window to viewport transformation:

• ***World Coordinate –*** It is the Cartesian coordinate that we want to represent in the viewport. \
• ***Device Coordinate –*** It is the screen coordinate where the objects are to be displayed, so at any world coordinate is associated a device coordinate. \
• ***Window –*** It is the area on world coordinate selected for display.\
• ***ViewPort –*** It is the area on the device coordinate where graphics is to be displayed.\

It may be possible that the size of the Viewport is much smaller or greater than the Window. In these cases, we have to correctly positionate any value according to the dimension of the Viewport and, for this, we need some mathematical calculations.
We define:
```
(xբ, yբ) as a point in the World Window
(xᵥ, yᵥ) as the corresponding  point in the associated Viewport
```
We want to calculate the coordinate (xᵥ,yᵥ) and to do so can be followed the procedure below.

![Foglio di brutta-4](https://user-images.githubusercontent.com/78324346/138499181-ad596cd4-0f95-4ad1-bc78-975a99d41d43.jpg)

What seen in a mathematical way can be written in code as shown in the next block of code. \
The object "r" is the viewport in which we want to represent a point represented by (X_World, Y_World). The variables MinX, MaxX, MinY and MaxY are defined as their homonyms above. In this case the values accepted range from 0 to 250 for both X and Y. \
The two functions apply to a value, represented in the real world window, the trasformation to represent it in the viewport. There is one function for the X-axis values and one for Y-axis values.

{% highlight C# %}
public int MinX = 0;
public int MaxX = 250;
public int MinY = 0;
public int MaxY = 250;
int RangeX = MaxX - MinX;
int RangeY = MaxY - MinY;
        
int X_Viewport(double X_World)
{
    return (int)(r.Left + r.Width * (X_World - MinX_Window) / RangeX);
}

int Y_Viewport(double Y_World)
{
    return (int)(r.Top + mv_r.r.Height - r.Height * (Y_World - MinY_Window)/RangeY);
}
{% endhighlight %}

[1] [https://www.geeksforgeeks.org/window-to-viewport-transformation-in-computer-graphics-with-implementation/](https://www.geeksforgeeks.org/window-to-viewport-transformation-in-computer-graphics-with-implementation/)
