\page legato_qs_mzef_cu_tm4301b_ssd1963_X legato_qs_mzef_cu_tm4301b_ssd1963.X
[TOC]

## Defining the Architecture

<img src="legato_qs_e70_xu_tm4301b_ssd1963_arch.png"/>

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

<img src="legato_qs_e70_xu_tm4301b_ssd1963_pg.png"/>

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

•<img src="legato_qs_e70_xu_tm4301b_ssd1963_conf1.png"/>

## Running the Demonstration

The application first boots to an animated Splash Screen. Once the Splash Screen animation completes, the application boots to a Main Screen.

When at rest, the demo will cycle through idle sprite animations. Various areas of the screen are touch interactive

<img src="legato_adv_e54_cu_cpro_parallel_img1.png"/>

If initiated to run, the lamb sprite will run to the end of the screen, and play out a sequence of smacking into a wall, hurt and dizzy animations.

<img src="legato_adv_e54_cu_cpro_parallel_img2.png"/>

Tap Jump and the lamb will play out a jump animation.

<img src="legato_adv_e54_cu_cpro_parallel_img3.png"/>

Info Screen describes the features supported by this demo

<img src="legato_adv_e54_cu_cpro_parallel_img4.png"/>
