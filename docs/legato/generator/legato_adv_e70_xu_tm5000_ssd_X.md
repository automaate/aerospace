\page legato_adv_e70_xu_tm5000_ssd1963_X legato_adv_e70_xu_tm5000_ssd1963.X
[TOC]

## Defining the Architecture

<img src="legato_adv_e70_xu_tm4301b_ssd1963_arch.png" width="480" height="272" />

The architecture for this configuration is the SAM E70 Xplained Ultra + 4.3” WQVGA with SSD1963 GFX Interface Card interface through the 16-bit 8080 mode.

The SSD1963 is connected
to the SAM E70 thru the SMC peripheral and GPIOs which are used to
send 16-bit parallel data/commands and to bit-bang control signals
to the SSD1963 controller, respectively. The frame buffer is stored
externally in the SSD1963 controller.

Input on the display panel is received thru the PCAP capacitive touch controller, which sends a notification to the Touch Input Driver. The Touch Input Driver reads the touch information over I2C and sends the touch event to the Graphics Library thru the Input System Service.

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

<img src="legato_adventure_e70_xu_wvga_ssd1963_pg.png" width="480" height="272" />

In this configuration, the SSD1963 display controller is used to send
the display data and timing to a WQVGA display. The SSD1963 is connected
to the SAM E70 thru the SMC peripheral and GPIOs which are used to
send 16-bit parallel data/commands and to bit-bang control signals
to the SSD1963 controller, respectively. The frame buffer is stored
externally in the SSD1963 controller.

## Building the Application

The parent directory for this application is gfx/apps/legato_quickstart. To
build this application, use MPLAB X IDE open the
gfx/apps/legato_quickstart/firmware/legato_adv_e70_xu_tm5000_ssd1963.X
project file.

The following table lists configuration properties: 

| Project Name  | BSP Used |Graphics Template Used | Description |
|---------------| ---------|---------------| ---------|
| legato_adv_e70_xu_tm5000_ssd1963.X | sam_e70_xplained_ultra | Legato Graphics w/ PDA TM4301B Display | sam_e70_xplained_ultra with SSD1963 GFX Interface and 5� WVGA PCAP Touch display |
 
> **_NOTE:_**  This application may contain custom code that is marked by the comments // START OF CUSTOM CODE ... and // END OF CUSTOM CODE. When using the MPLAB Harmony Configurator to regenerate the application code, use the "ALL" merging strategy and do not remove or replace the custom code.

## Configuring the Hardware

The final setup should be:

<img src="legato_qs_e70_xu_tm4301b_conf1.png"/>

Configuring the 4.3� WQVGA Display requires disconnecting the ribbon cable that connects the display to the interposer board.

<img src="legato_qs_e70_xu_tm4301b_conf2.png"/>

First, release the ribbon cable from the interposer board. Next, release the black clamp on the E70�s J2 connector and turn the display over. Finally, insert the ribbon cable into J2 and close the clamp

<img src="legato_qs_e70_xu_tm4301b_conf3.png"/>

The board and display are powered by a Micro B � USB A cable from PC to the �Debug USB� port on the E70 board. The ICD4 Debugger and ICD4/PICKit4 Adapter Board are connected as shown above.

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
