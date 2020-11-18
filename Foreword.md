The first step of the physical creation of the FeedBack device is planning, which involves mapping.

While there are ways to load bitmaps through pngs, one of the greatest goals of FeedBack is to have minimal dependencies, so we can not store pngs on the M4 device itself

We could consider making the bitmaps by hand or loading them to the device, however this is prone to small micro-errors when increasing the resolution or pixel count of the display.

My first initial thought was to convert an SVG into bmp, yet the file format was not interpretable to circuitPython, so I would have to describe it geometrically myself



