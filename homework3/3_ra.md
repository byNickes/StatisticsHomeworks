**Made by Nicolò Baroncini (1834907)**

## Research about application(3_RA)
### Do a comprehensive research about the GRAPHICS object and all its members (to get ready to create any statistical chart.)
The graphics object is part of Windows GDI+ which is a class-based API. It enables applications to use graphics and formatted text on both the video display and the printer.\
The services of Windows GDI+ fall into the following three broad categories:

• ***2-D vector graphics***\
• ***Imaging***\
• ***Typography***

We are now interested in ***2-D vector graphics*** since it contains the Graphics class.\
Vector graphics involves drawing primitives (such as lines, curves, and figures) that are specified by sets of points on a coordinate system. For example, a straight line can be specified by its two endpoints, and a rectangle can be specified by a point giving the location of its upper-left corner and a pair of numbers giving its width and height. A simple path can be specified by an array of points to be connected by straight lines.\
GDI+ provides classes that store information about the primitives themselves, classes that store information about how the primitives are to be drawn, and classes that actually do the drawing.

In this category falls the class ***Graphics*** which has methods for drawing lines, rectangles, paths, and other figures. It encapsulates a GDI+ drawing surface, which can be a Bitmap or a Image object, where the figures are drawn. The drawing surface can be then associated to an image container, like a PictureBox, to display the drawing.\
We can divide Graphics class methods into three categories: draw and fill. Draw methods are used to draw lines, curves, and outer boundaries of closed curves and images. Fill methods fill the interior area of graphics objects.

First let's see the attributes of the Graphics class:\
![Schermata 2021-10-13 alle 17 09 59](https://user-images.githubusercontent.com/78324346/137161593-e5774d05-374f-451d-af96-ba2520198be5.png)

***Draw methods*** of the Graphics class are used to draw lines, curves, and outer boundaries of closed curves and images. \
The next table shows the draw methods available:

![Schermata 2021-10-13 alle 16 55 59](https://user-images.githubusercontent.com/78324346/137158837-f1ea08d0-cb64-4adb-8e54-71999814f94e.png)

***Fill methods*** are used to fill the interior of graphics shapes. You can fill only certain graphics shapes, hence, there are only a few Fill methods available in the Graphics class.\
The following table shows the fill methods available in GDI+:
![Schermata 2021-10-13 alle 17 06 03](https://user-images.githubusercontent.com/78324346/137160721-36790a92-0db8-416a-b23b-1b368e729f8e.png)

[1] [https://en.wikipedia.org/wiki/Graphics_Device_Interface](https://en.wikipedia.org/wiki/Graphics_Device_Interface) \
[2] [https://docs.microsoft.com/en-us/windows/win32/gdiplus/-gdiplus-gdi-start](https://docs.microsoft.com/en-us/windows/win32/gdiplus/-gdiplus-gdi-start) \
[3] [https://docs.microsoft.com/en-us/windows/win32/gdiplus/-gdiplus-the-three-parts-of-gdi--about](https://docs.microsoft.com/en-us/windows/win32/gdiplus/-gdiplus-the-three-parts-of-gdi--about) \
[4] [https://docs.microsoft.com/it-it/dotnet/api/system.drawing.graphics?view=windowsdesktop-5.0](https://docs.microsoft.com/it-it/dotnet/api/system.drawing.graphics?view=windowsdesktop-5.0) \
[5] [https://www.c-sharpcorner.com/uploadfile/mahesh/the-graphics-class/](https://www.c-sharpcorner.com/uploadfile/mahesh/the-graphics-class/) \
[6] [https://www.c-sharpcorner.com/UploadFile/mahesh/fill-methods-in-gdi/](https://www.c-sharpcorner.com/UploadFile/mahesh/fill-methods-in-gdi/)
