CG-ppmImageRenderer
===================

Draw ppm image to disk by reading the pixels using the custom built Gz Graphics library.

Build a small but useful graphics library. We'll call it the Gz library, and all functions, vars, etc, will be named accordingly.  
Code interfaces consistency will be established by the use of prepared include files and an Application Program Interface (API). 

• All displays are addressed by pixel coordinates, and accept or return pixel values. 
• Upper left pixel is (x=0, y=0).  x increases to the right, and y increases downward (raster order). 
• A flush operation writes the accumulated pixels to a disk file.  
Disk files will be in the "ppm" file format so that "xv" can be used to display and convert them. 
• ppm files are color image files that have an ascii header with xs and ys image-dimensions and a binary 3-byte pixel format: P6 xs yx 255\n  rgbrgbrgbrgb. 
• A sample ppm header might be:  P6 512 480 255. 
• This would be correct for an image with 512 pixels horizontally and 480 pixels vertically. 
• Display objects hide the organization of pixel memory and its allocation from the application and renderer. 
• Only applications create, free, and flush Displays. Display class and size are determined by the application. 
Pixels are written by the Renderer using the Put call. 
• Defining the API interfaces makes the application and Renderer library display-independent.