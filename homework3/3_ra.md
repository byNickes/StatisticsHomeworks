**Made by Nicolò Baroncini (1834907)**

## Research about application(3_RA)
### Do a comprehensive research about the GRAPHICS object and all its members (to get ready to create any statistical chart.)
The graphics object is part of Windows GDI+ which is a class-based API. It enables applications to use graphics and formatted text on both the video display and the printer.\
The services of Windows GDI+ fall into the following three broad categories:

• ***2-D vector graphics***\
• ***Imaging***\
• ***Typography***

##### 2-D vector graphics
Vector graphics involves drawing primitives (such as lines, curves, and figures) that are specified by sets of points on a coordinate system. For example, a straight line can be specified by its two endpoints, and a rectangle can be specified by a point giving the location of its upper-left corner and a pair of numbers giving its width and height. A simple path can be specified by an array of points to be connected by straight lines.\
GDI+ provides classes that store information about the primitives themselves, classes that store information about how the primitives are to be drawn, and classes that actually do the drawing.

In this category falls the class ****Graphics**** which has methods for drawing lines, rectangles, paths, and other figures. It encapsulates a GDI+ drawing surface, which can be a Bitmap or a Image object, where the figures are drawn. The drawing surface can be then associated to an image container, like a PictureBox, to display the drawing.\
Some methods of Graphics class to draw figures are DrawLine, DrawArc, DrawClosedCurve, DrawPolygon, and DrawRectangle.

##### Imaging
Certain kinds of pictures are difficult or impossible to display with the techniques of vector graphics. For example a high-resolution digital photograph of a crowded baseball stadium would be even more difficult to create with vector techniques. Images of this type are stored as bitmaps, arrays of numbers that represent the colors of individual dots on the screen. Data structures that store information about bitmaps tend to be more complex than those required for vector graphics, so there are several classes in GDI+ devoted to this purpose.

##### Typography
Typography is concerned with the display of text in a variety of fonts, sizes, and styles.

[1] [https://en.wikipedia.org/wiki/Graphics_Device_Interface](https://en.wikipedia.org/wiki/Graphics_Device_Interface) \
[2] [https://docs.microsoft.com/en-us/windows/win32/gdiplus/-gdiplus-gdi-start](https://docs.microsoft.com/en-us/windows/win32/gdiplus/-gdiplus-gdi-start) \
[3] [https://docs.microsoft.com/en-us/windows/win32/gdiplus/-gdiplus-the-three-parts-of-gdi--about](https://docs.microsoft.com/en-us/windows/win32/gdiplus/-gdiplus-the-three-parts-of-gdi--about)
[4] [https://docs.microsoft.com/it-it/dotnet/api/system.drawing.graphics?view=windowsdesktop-5.0](https://docs.microsoft.com/it-it/dotnet/api/system.drawing.graphics?view=windowsdesktop-5.0)
