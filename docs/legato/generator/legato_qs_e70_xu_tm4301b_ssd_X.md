\page legato_qs_e70_xu_tm4301b_ssd1963_X legato_qs_e70_xu_tm4301b_ssd1963.X
[TOC] 

## Defining the Architecture

<img src="legato_qs_e70_xu_tm4301b_ssd1963_arch.png" width="480" height="272" />

In this configuration, the SSD1963 display controller is used to send
the display data and timing to a WQVGA display. The SSD1963 is connected
to the SAM E70 thru the SMC peripheral and GPIOs which are used to
send 16-bit parallel data/commands and to bit-bang control signals
to the SSD1963 controller, respectively. The frame buffer is stored
externally in the SSD1963 controller.

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

<img src="legato_qs_e70_xu_tm4301b_ssd1963_pg.png" width="480" height="272" />

The Project Graph diagram shows the Harmony components that are
included in this application. Lines between components are drawn to
satisfy components that depend on a capability that another component
provides.

Adding the ?SAM E70 XPlained Ultra BSP? and ?Legato Graphics w/ PDA
TM4301B Display? Graphics Template component into the project graph
will automatically add the components needed for a graphics project
and resolve their dependencies. It will also configure the pins needed
to drive the external peripherals like the display and the touch
controller.

By default, the template is configured to use the Low-Cost
Controller-less (LCC) interface to the display. To configure the
project for an SSD1963, set the Display Interface setting for the
Legato component from LCC to SSD1963.

## Building the Application

The parent directory for this application is gfx/apps/legato_quickstart. To build this application, use MPLAB X IDE open the gfx/apps/legato_quickstart/firmware/legato_qs_mzef_cu_tm4301b_ssd1963.X project file.

The following table lists configuration properties: 

| Project Name  | BSP Used |Graphics Template Used | Description |
|---------------| ---------|---------------| ---------|
| legato_qs_e70_xu_tm4301b_ssd1963.X | sam_e70_xplained_ultra  | Legato Graphics w/ PDA TM4301B Display | Legato GFX on SAM E70 Xplained Ultra board with PDA TM4301B 480x272 (WQVGA) Display and SSD1963 display driver  |

> **_NOTE:_**  This application may contain custom code that is marked by the comments // START OF CUSTOM CODE ... and // END OF CUSTOM CODE. When using the MPLAB Harmony Configurator to regenerate the application code, use the "ALL" merging strategy and do not remove or replace the custom code.

## Configuring the Hardware

The final hardware set-up should be:

<img src="legato_qs_e70_xu_tm4301b_ssd1963_conf1.png"/>

## Running the Demonstration

When power-on is successful, the demonstration will display a similar menu to that shown in the following figure (different configurations may have slight variation in the screen aspect ratio):

<img src="legato_qs_e70_xu_tm4301b_run1.png"/>

When Make changes. Generate. Run. is touched, the button will toggle with each individual touch.

<img src="legato_qs_e70_xu_tm4301b_run2.png"/>
