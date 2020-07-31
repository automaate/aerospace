\page legato_qs_mzda_intddr_sk_meb2_tm4301b_X legato_qs_mzda_intddr_sk_meb2_tm4301b.X
[TOC]

## Defining the Architecture

![](https://microchip-mplab-harmony.github.io/gfx_apps/mzda_sk_meb2_wqvga_arch.png)

For this configurations, the application uses the Graphics Library to render graphics to the display. The Graphics library passes draw commands into the GPU Library, which in turn draws the widgets and images to the frame buffer stored in the DDR memory. Via the DDR2 Memory Controller, the GLCD display controller peripheral continuously transfers frame data from the frame buffers onto the LCD display.

The application also features user touch input through the integrated touch screen on the display panel. Touch input from the touch controller travels through the I2C port, and the Input System Service acquires the touch input information from the touch and I2C drivers. The Input System Service sends touch events to the Graphics library which processes these events and updates the frame data.

The block diagram(s) below show(s) the various software and hardware blocks used in this application.

### Demonstration Features 

* Legato Graphics Library
* GLCD display controller and NANO 2D GPU
* 32-bit RGBA Color Mode Frame Buffer in DDR memory
* Input system service and touch driver
* Time system service, timer-counter peripheral library and driver
• RLE compressed RGB image in internal flash

## Creating the Project Graph

![](https://microchip-mplab-harmony.github.io/gfx_apps/legato_mzda_intddr.png)

The Project Graph diagram below shows the Harmony components that are included in this application. Lines between components are drawn to satisfy components that depend on a capability that another component provides.

Adding the “PIC32MZ DA Starter Kit BSP” and “Legato Graphics w/ PDA TM4301B Display” Graphics Template component into the project graph will automatically add the components needed for a graphics project and resolve their dependencies. It will also configure the pins needed to drive the external peripherals like the display and the touch controller.

## Building the Application

The parent directory for this application is gfx/apps/legato_quickstart. To build this application, use MPLAB X IDE to open the gfx/apps/legato_quickstart/firmware/legato_qs_mzda_intddr_sk_meb2_tm4301b.X project file.

The following table lists configuration properties:  

| Project Name  | BSP Used |Graphics Template Used | Description |
|---------------| ---------|---------------| ---------|
| legato_qs_mzda_intddr_sk_meb2_tm4301b.X | PIC32MZ DA Starter Kit | Legato graphics w/ PDA TM4301b Display| Legato graphics on PIC32MZ DA with Internal DDR Starter Kit, MEBII and PDA TM4301b Display. |

> **_NOTE:_**  This application may contain custom code that is marked by the comments // START OF CUSTOM CODE ... and // END OF CUSTOM CODE. When using the MPLAB Harmony Configurator to regenerate the application code, use the "ALL" merging strategy and do not remove or replace the custom code.

## Configuring the Hardware

The final setup should be: 

Configure the hardware as follows:
• Attach the RGB565 GFX Interface Card to the J601 connector on the PIC32MZ EF Curiosity 2.0 board.
• Connect the ribbon cable from the WQVGA display to the J2 connector on the RGB565 GFX Interface card.
• Connect a USB cable from the host computer to the DEBUG USB port on the PIC32MZ EF Curiosity 2.0 board. This USB connection is used for power, code download and debugging.
The final hardware setup should be: 

![](https://microchip-mplab-harmony.github.io/gfx_apps/mzda_sk_intddr_wqvga_hardware.png)

Connect the PIC32MZ DA Starter Kit to the MEB II board

![](https://microchip-mplab-harmony.github.io/gfx_apps/mzda_sk_intddr_wqvga_hardware2.png)

Power up the board by connecting the power adapter to J3 power connector on the MEB II board or a powered USB cable to the USB DEBUG port on the Starter Kit board.

## Running the Demonstration

![](https://microchip-mplab-harmony.github.io/gfx_apps/aria_quickstart_screen.png)

When Make changes. Generate. Run. is touched, the button will toggle with each individual touch.

![](https://microchip-mplab-harmony.github.io/gfx_apps/aria_quickstart_screen_pressed.png)