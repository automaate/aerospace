\page MultipleLayers Multiple Layers
[TOC]

## Using Multiple layers

The GLCD display controller supports 3 layers which are used to accelerate graphics features like the sliding panels

<img src="legato_cc_mzda_cu_tm5000_ui6.png"/>

How can I fit a 3-layer WVGA design in the 640kB internal SRAM?
* Layer 0 frame is full WVGA 800x480 (384kB), single-buffered
* Layer 1 frame is 400x50 (20kB), single-buffered
* Layer 2 frame is 300x350 (105kB), single-buffered
* Total memory used for frame buffer is only 509kB, with 131kB left (heap, etc)