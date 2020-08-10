\page LegatoFlash Quickstart Flash

<img src="legato_flash.png" width="480" height="272" />

The legato_flash demonstration application serves as an external memory programmer to flash the off-chip non-volatile memory.

The legato_flash demonstration application serves as an external memory programmer to flash the off-chip non-volatile memory with the resources held on an Memory Storage Device (MSD), such as a USB or a SD card, which can then be accessed by other applications saving on-chip memory for other programs and resources.

The application legato_quickstart_external_resources in MPLAB Harmony needs to use preloaded images/fonts from QSPI flash external non-volatile memory. This would require legato_flash to flash the required image and font resources onto the QSPI flash. Refer to legato_quickstart_external_resources for usage model information.

This demonstration runs on: 

| MPLABX Configuration | Board Configuration |
| -------------------- | ------------------- |
| [legato_fl_e54_cult_cpro_parallel.X](legato_fl_e54_cult_cpro_parallel_X.html)| [SAM E54 Curiosity Ultra Development Board](https://www.microchip.com/Developmenttools/ProductDetails/DM320210) using external ILI9488 controller to drive the [maXTouch® Curiosity Pro Board](https://www.microchip.com/Developmenttools/ProductDetails/AC320007) |
| [legato_fl_e70_xu_tm4301b.X](legato_fl_e70_xu_tm4301b_X.html)|  [SAM E70 Xplained Ultra Evaluation Kit](https://www.microchip.com/Developmenttools/ProductDetails/DM320113) using LCC software display controller to drive the [High-Performance 4.3\" WQVGA Display Module with maXTouch® Technology](https://www.microchip.com/DevelopmentTools/ProductDetails/PartNO/AC320005-4) |
| [legato_fl_mzef_cu_tm4301b.X](legato_fl_mzef_cu_tm4301b_X.html) | [Curiosity PIC32MZ EF 2.0 Development Board](https://www.microchip.com/Developmenttools/ProductDetails/DM320209) using LCC software display controller to drive the [High-Performance 4.3\" WQVGA Display Module with maXTouch® Technology](https://www.microchip.com/DevelopmentTools/ProductDetails/PartNO/AC320005-4) |

## Description

Applications that use large images or multiple page menu screens, which require several images or large or multiple font packages, etc., have a very large memory requirement for their graphics resources. In such applications, storing these graphics resources on-chip may result in insufficient memory or may be prohibitive to a possible cost benefit. A solution is to store the graphics resources to off-chip memory, such as non-volatile memory, thereby preserving the on-chip memory for program memory and allowing for more complex functional features. 

The legato_flash application flashes the .hex file containing the binary data of the external graphics resources, in this case QSPI.hex, into the external non-volatile memory. The resource file is copied from the computer to a USB Flash drive, which has a FAT32 file system installed. The USB Flash drive is then plugged into SAM E70 Curiosity Ultra development board and the application scans the MSD for the resource file. The legato_flash application copies the resource file sector by sector and flashes the binary resource content onto the QSPI Flash external memory.

[TOC]
\subpage legato_fl_e54_cult_cpro_parallel_X
\subpage legato_fl_e70_xu_tm4301b_X
\subpage legato_fl_mzef_cu_tm4301b_X