\page ScreenTearing Screen Tearing
[TOC]

### Minimizing Screen Tearing

Frame buffers are single-buffered, yet screen tearing is minimal. 

How is this achieved?

* Screen tearing is minimal since updates are mostly on small areas of the frame (icons, buttons, etc)
* Frame redraws are fast since frame data is smaller with indexed colors
* Full screen draws are ‘hidden from view’ by dimming the backlight between screen transitions (e.g., between splash and main screen)
* Graphics effects like panel sliding are achieved using GLCD layers which do not require a frame redraw

