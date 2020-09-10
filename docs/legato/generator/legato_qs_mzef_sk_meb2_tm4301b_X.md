\page legato_qs_mzef_sk_meb2_tm4301b_X legato_qs_mzef_sk_meb2_tm4301b.X
[TOC]

## Defining the Architecture

<img src="legato_qs_mzef_sk_meb2_tm4301b_arch.png"/>

This configuration runs on the PIC32MZ EF Starter Kit with MEBII and WQVGA display. A 16-bit RGB565 frame buffer is stored in the internal SRAM, and the Low Cost Controller-less (LCC) display driver is used to manage the DMA that transfers the framebuffer contents to the display.

User touch input on the display panel is received thru the PCAP capacitive touch controller, which sends a notification to the Touch Input Driver. The Touch Input Driver reads the touch information over I2C and sends the touch event to the Graphics Library thru the Input System Service.

### Demonstration Features 

* Legato Graphics Library
* Input system service and touch driver
* Time system service, timer-counter peripheral library and driver
* Low-Cost Controller-less (LCC) display driver
* 16-bit RGB565 color depth support (65535 unique colors)
* EBI peripheral library and driver
* I2C driver
* JPEG image stored in internal flash

## Creating the Project Graph

![](https://microchip-mplab-harmony.github.io/gfx_apps/legato_qs_mzef_sk_meb2_tm4301b.X_pg.png)

The Project Graph diagram shows the Harmony components that are included in this application. Lines between components are drawn to satisfy components that depend on a capability that another component provides.

Adding the �PIC32MZ EF Starter Kit BSP� and �Legato Graphics w/ PDA TM4301B Display� Graphics Template components into the project graph will automatically add the components needed for a graphics project and resolve their dependencies. It will also configure the pins needed to drive the external peripherals like the display and the touch controller. 

## Building the Application

The parent directory for this application is gfx/apps/legato_quickstart. To build this application, use MPLAB X IDE to open the gfx/apps/legato_quickstart/firmware/legato_qs_mzef_sk_meb2_tm4301b.X project file.

The following table lists configuration properties:   

| Project Name  | BSP Used |Graphics Template Used | Description |
|---------------| ---------|---------------| ---------|
| legato_qs_mzef_sk_meb2_tm4301b.X | PIC32MZ EF Starter Kit| Legato Graphics w/ PDA TM4301B Display| PIC32MZ EF Starter Kit with MEBII and 4.3� WQVGA PCAP Touch display |

> **_NOTE:_**  This application may contain custom code that is marked by the comments // START OF CUSTOM CODE ... and // END OF CUSTOM CODE. When using the MPLAB Harmony Configurator to regenerate the application code, use the "ALL" merging strategy and do not remove or replace the custom code.

## Configuring the Hardware

On the MEB II, the EBIWE and LCD_PCLK (J9) must be jumpered to use the internal SRAM for graphics frame buffer. The J9 jumper is located on the bottom of the MEB II board, beneath where the starter kit is plugged into the board. Refer to the following figure for the exact location. 

<img src="legato_qs_mzef_sk_meb2_tm4301b_conf1.png"/>

Connect the PIC32MZ EF Starter Kit to the MEB II board.

<img src="legato_qs_mzef_sk_meb2_tm4301b_conf2.png"/>

Power up the board by connecting the power adapter to J3 power connector on the MEB II board or a powered USB cable to the USB DEBUG port on the Starter Kit board

The final hardware set-up should be: 

<img src="legato_qs_mzef_sk_meb2_tm4301b_conf3.png"/>

## Running the Demonstration

When power-on is successful, the demonstration will display a similar menu to that shown in the following figure (different configurations may have slight variation in the screen aspect ratio):

<img src="legato_qs_e70_xu_tm4301b_run1.png"/>

When Make changes. Generate. Run. is touched, the button will toggle with each individual touch.

<img src="legato_qs_e70_xu_tm4301b_run2.png"/>
