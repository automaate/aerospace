\page blank_qs_mzef_cu_wqvga_X blank_qs_mzef_cu_wqvga.X
[TOC]

## Defining the Architecture

<img src="legato_qs_mzef_cu_tm4301b_arch.png" width="480" height="272" />

This configuration runs on the PIC32MZ EF Curiosity 2.0 with RGB565 GFX
Interface board and WQVGA display. A 16-bit RGB565 frame buffer is
stored in the internal SRAM, and the Low Cost Controller-less (LCC)
display driver is used to manage the DMA that transfers the framebuffer
contents to the display via the EBI peripheral.

User touch input, if any, is received thru the PCAP capacitive touch
controller, which sends a notification to the Touch Input Driver. The
Touch Input Driver reads the touch information over I2C and sends the
touch event to the Graphics Library thru the Input System Service.

### Demonstration Features 

* 3rd-Party graphics library interface
* Low-Cost Controller-less (LCC) display driver 
* 16-bit RGB565 color depth support (65535 unique colors) 
* EBI peripheral library and driver 
* RAW image stored in internal flash 

## Creating the Project Graph

<img src="blank_qs_mzef_cu_wqvga_pg.png" width="480" height="272" />

The Project Graph diagram shows the Harmony components that are included in this application. Lines between components are drawn to satisfy components that depend on a capability that another component provides. 

Adding the **PIC32MZ EF Curiosity 2.0 BSP** and **Legato Graphics w/ PDA TM4301B Display** Graphics Template component into the project graph will automatically add the components needed for a graphics project and resolve their dependencies. It will also configure the pins needed to drive the external peripherals like the display and the touch controller.

## Building the Application

The parent directory for this application is gfx/apps/blank_quickstart. To build this application, use MPLABX IDE to open the gfx/apps/blank_quickstart/firmware/blank_qs_mzef_cu_tm4301b.X project file.

The following table lists configuration properties: 

| Project Name  | BSP Used |Graphics Template Used | Description |
|---------------| ---------|---------------| ---------|
| blank_qs_mzef_cu_wqvga.X | PIC32MZ EF Curiosity 2.0 | PDA TM4301B display | PIC32MZ EF Curiosity 2.0 with RGB565 GFX Interface and 4.3\" WQVGA PCAP Touch display |

> **_NOTE:_**  This application may contain custom code that is marked by the comments // START OF CUSTOM CODE ... and // END OF CUSTOM CODE. When using the MPLAB Harmony Configurator to regenerate the application code, use the "ALL" merging strategy and do not remove or replace the custom code.

## Configuring the Hardware

Configure the hardware as follows:

* Attach the RGB565 GFX Interface Card to the J601 connector on the PIC32MZ EF Curiosity 2.0 board.
* Connect the ribbon cable from the WQVGA display to the J2 connector on the RGB565 GFX Interface card.
* Connect a USB cable from the host computer to the DEBUG USB port on the PIC32MZ EF Curiosity 2.0 board. This USB connection is used for power, code download and debugging.

The final hardware setup should be:  

<img src="legato_qs_mzef_cu_tm4301b_conf1.png"/>

## Running the Demonstration

Once the board is powered on, the application will run and show the following image on the display panel.

<img src="blank_qs_mzda_intddr_sk_meb2_wqvga.png"/>