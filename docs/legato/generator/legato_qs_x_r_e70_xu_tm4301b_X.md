\page legato_qs_x_r_e70_xu_tm4301b_X legato_qs_x_r_e70_xu_tm4301b.X
[TOC]

## Defining the Architecture

<img src="legato_qs_x_r_e70_xu_tm4301b_arch.png" width="800" height="480" />

This configuration runs on the SAM E70 Xplained Ultra with maXTouch Curiosity Pro Display.

User touch input on the display panel is received thru the PCAP capacitive touch controller, which sends a notification to the Touch Input Driver. The Touch Input Driver reads the touch information over I2C and sends the touch event to the Graphics Library thru the Input System Service.

The application reads the binary data from the external non-volatile memory via the QSPI peripheral configured with the SST26 driver.

### Demonstration Features 

* Legato Graphics Library 
* Input system service and touch driver
* Time system service, timer-counter peripheral library and driver
* Low-Cost Controllerless driver
* 16-bit RGB565 color depth
* EBI peripheral library and driver
* I2C peripheral library and driver
* SST26 QSPI driver
* Images and Fonts for user interface stored in external flash (NVM)


## Creating the Project Graph

<img src="legato_qs_x_r_e70_xu_tm4301b_pg.png" width="800" height="480" />

The Project Graph diagram shows the Harmony components that are included in this application. Lines between components are drawn to satisfy components that depend on a capability that another component provides.

Adding the **SAM E70 Xplained Ultra BSP** and **Legato Graphics w/ PDA TM4301b Display** Graphics Template component into the project graph.

This will automatically add the components needed for a graphics project and resolve their dependencies. It will also configure the pins needed to drive the external peripherals like the display and the touch controller.

Additional components to support QSPI and SST26 needs to be added and connected manually.
For QSPI access, make sure all 6 pins for QSPI is mapped.
 
<img src="legato_qs_x_r_e70_xu_tm4301b_pg2.png" />

## Building the Application

The parent directory for this application is gfx/apps/legato_quickstart_ext_res. To build this application, use MPLAB X IDE open the gfx/apps/legato_quickstart_ext_res/firmware/legato_qs_e70_xu_tm4301b.X project file.

The following table lists configuration properties:  

| Project Name  | BSP Used |Graphics Template Used | Description |
|---------------| ---------|---------------| ---------|
| legato_qs_x_r_e70_xu_tm4301b.X | SAM E70 Xplained Ultra | Legato graphics w/ PDA TM4301b Display | SAM E70 Xplained Ultra with 4.3” WQVGA PCAP Touch display |

> **_NOTE:_**  This application may contain custom code that is marked by the comments // START OF CUSTOM CODE ... and // END OF CUSTOM CODE. When using the MPLAB Harmony Configurator to regenerate the application code, use the "ALL" merging strategy and do not remove or replace the custom code.

## Configuring the Hardware

The final setup should be: 

<img src="legato_qs_x_r_e70_xu_tm4301b_conf1.png"/>

## Running the Demonstration.png

When power-on is successful, the following screen will appear on the display

<img src="legato_qs_x_r_e70_xu_tm4301b_run1.png" />

Pressing the button will cause the application to load a new image.  The image cycles in order from Uncompressed RAW with Direct Blit, Uncompressed RAW, Run-Length Encoded (RLE) RAW, to JPEG.

The MPLAB Harmony Graphics Suite logo is also a button.  Pressing the logo will toggle the application between English and Simplified Chinese.
 
<img src="legato_qs_x_r_e70_xu_tm4301b_run2.png" />

Note that all images and glyphs are retrieved from external NVM via QSPI.  The application is purposely setup in single-buffer configuration to allow visual inspection of the data retrieval speed of the various images and glyphs.
