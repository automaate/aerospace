\page SpriteAnimation Sprite Animation
[TOC]

**Sprite Animation**

* A series of pre-rotated needle images are pre-processed and stored in DDR
* GLCD layers 1 and 2 are used to display the left and right needles
* To run the needle animation, the GLCD layer start address is set to the location of the images in DDR
* The GLCD layer position is also adjusted to show the needles at the correct location on the screen
* The image address in DDR, image size and position on the screen are stored in an array in order based on the angle position
* This array is used by the application to reference the image address, size and position and sets these values to GLCD layer 
* The application uses the graphics canvas to configure the GLCD for image sprite animation

<img src="legato_db_mzda_cu_tm5000_ui4.png" width="480" height="272" />