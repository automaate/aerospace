\page LegatoClimateControl ClimateControl Application
[TOC]
\subpage legato_cc_mzda_cu_tm5000_X

<img src="legato_climate_control.png" width="480" height="272" />

This demonstration emulates an interactive, touch-enabled vehicle climate control User Interface (UI).

It runs on the PIC32MZ DA Curiosity board with a 24-bit passthrough graphics interface card and a 5” WVGA display. Because all frame buffers are stored in SRAM, the ideal target for the demo application is the PIC32MZ DAK/DAL with no DDR.

This demonstration runs on: 

| MPLABX Configuration | Board Configuration |
| -------------------- | ------------------- |
| [legato_cc_mzda_cu_tm5000.X](legato_cc_mzda_cu_tm5000_X.html)| Curiosity PIC32MZ DA 2.0 Development Board using GLCD peripheral display controller to drive the [High-Performance WVGA LCD Display Module with maXTouch ® Technology](https://www.microchip.com/DevelopmentTools/ProductDetails/PartNO/AC320005-4)|