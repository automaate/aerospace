\page legato_qs_mzef_cu_tm4301b_ssd1963_X legato_qs_mzef_cu_tm4301b_ssd1963.X
[TOC]

## Defining the Architecture

<img src="legato_qs_mzef_cu_tm4301b_ssd_arch.png" width="480" height="272" />

This configuration runs on the Legato Graphics Library on the PIC32MZ EF Curiosity 2.0 with an extern SSD1963 display controller driving a WQVGA display.

The SSD1963 display controller is used to send the display data and timing to a display. The SSD1963 is connected to the PIC32MZ EF thru the EBI peripheral and GPIOs which are used to send 16-bit parallel data/commands and control signals to the SSD1963 controller. The frame buffer is stored externally in the SSD1963 controller.

User touch input on the display panel is received thru the PCAP capacitive touch controller, which sends a notification to the Touch Input Driver. The Touch Input Driver reads the touch information over I2C and sends the touch event to the Graphics Library thru the Input System Service.

## Demonstration Features 

* Legato Graphics Library
* Input system service and touch driver
* Time system service, timer-counter peripheral library and driver
* SSD1963 display controller driver
* 16-bit RGB565 color depth support (65535 unique colors)
* EBI peripheral library and driver
* I2C peripheral library and driver
* JPEG image stored in internal flash

## Creating the Project Graph

<img src="legato_qs_mzef_cu_tm4301b_ssd_pg.png" width="480" height="272" />

The Project Graph diagram shows the Harmony components that are included in this application. Lines between components are drawn to satisfy components that depend on a capability that another component provides.

Adding the **PIC32MZ EF Curiosity 2.0 BSP** and **Legato Graphics w/ Xplained Pro Display** Graphics Template components into the project graph will automatically add the components needed for a graphics project and resolve their dependencies. It will also configure the pins needed to drive the external peripherals like the display and the touch controller.

To configure the project for an SSD1963, set the Display Interface setting for the **Legato Graphics w/ PDA TM4301B Display** component to SSD1963.
 
## Building the Application

The parent directory for this application is gfx/apps/legato_quickstart. To build this application, use MPLAB X IDE open the gfx/apps/legato_quickstart/firmware/legato_qs_mzef_cu_tm4301b_ssd1963.X project file.

The following table lists configuration properties: 

| Project Name  | BSP Used |Graphics Template Used | Description |
|---------------| ---------|---------------| ---------|
| legato_qs_mzef_cu_tm4301b_ssd1963.X | PIC32MZ EF Curiosity 2.0| Legato Graphics w/ PDA TM4301B Display | PIC32MZ EF Curiosity 2.0 with SSD1963 GFX Interface and 4.3\" WQVGA PCAP Touch display |
 
> **_NOTE:_**  This application may contain custom code that is marked by the comments // START OF CUSTOM CODE ... and // END OF CUSTOM CODE. When using the MPLAB Harmony Configurator to regenerate the application code, use the "ALL" merging strategy and do not remove or replace the custom code.

## Configuring the Hardware

Configure the hardware as follows:

* Attach the RGB565 GFX Interface Card to the J601 connector on the PIC32MZ EF Curiosity 2.0 board.
* Connect the ribbon cable from the WQVGA display to the J2 connector on the RGB565 GFX Interface card.
* Connect a USB cable from the host computer to the DEBUG USB port on the PIC32MZ EF Curiosity 2.0 board. This USB connection is used for power, code download and debugging.

The final hardware setup should be: 

![](https://microchip-mplab-harmony.github.io/gfx/lcc_rgb565_mxt_mzef_cu_cf1.png)

## Running the Demonstration

When power-on is successful, the demonstration will display a similar menu to that shown in the following figure (different configurations may have slight variation in the screen aspect ratio): 

When power-on is successful, the demonstration will display a similar menu to that shown in the following figure (different configurations may have slight variation in the screen aspect ratio):

<img src="legato_qs_e70_xu_tm4301b_run1.png"/>

When Make changes. Generate. Run. is touched, the button will toggle with each individual touch.

<img src="legato_qs_e70_xu_tm4301b_run2.png"/>