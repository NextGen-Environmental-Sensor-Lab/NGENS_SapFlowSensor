## 2023-04-07

Starting from scratch, in KiCad.

Microcontroller: CubeCell Dev-Board Plus
    https://resource.heltec.cn/download/Manual%20Old/AB02%20User%20Maunal.pdf
    Can run on 6V input

ADC
    https://www.adafruit.com/product/1085
    We should use the A+ and A- (AVDD and AGND) pins for the thermistors. Cleaned up versions of VCC and GND, ferrites and caps.
    Address pin can be connected to GND, VDD, SDA, or SCL for 4 addresses. We'll just use GND and VDD.


Using a right-angle header for the SD card reader, so it's easier to get the card out (and to save space)
    Same for RTC
    Don't forget to add right-angle header to the BOM!

For connecting the probes, screw terminals would be better
    https://www.digikey.com/en/products/detail/w%C3%BCrth-elektronik/691210910008/11478428


## 2023-04-09

Is it ok to pull the I2C lines up to 3.3V for the ADS1115?

Is it ok to pull the SQW/INT line on the DS3231 up to battery voltage? I would think not.

How is the PMOS power shutoff supposed to work? Seems backwards.


BOM additions
    Right-angle headers
    Screw terminals
        8 and 2
    Mounting hardware for TO-220s
    Mounting screws for the PCB to the enclosure


May want to make the PCB bigger and add screw holes to mount it inside the enclosure.


## 2023-04-10

Adapting the PCB to mount inside the case
    https://www.polycase.com/wh-02
    The drawing doesn't show the dimensions of the inside of the case... bummer
    The description says "2 PCB mounting bosses in base". So maybe the 4 things in the corners are for the external mounting, and the 2 centered things are for mounting the PCB.
    They look to be 8cm apart.
    Better use slots so there's some wiggle room.

Mounting screws
    The screws specified for mounting the PCB are different from the ones that come with it for mounting the box.
        M4 x 8mm
        The ones for outside are also M4, but thread cutting
    https://www.polycase.com/screws-007-50


BOM additions
    2   https://www.digikey.com/en/products/detail/te-connectivity-amp-connectors/282834-2/1150135
    2   https://www.digikey.com/en/products/detail/te-connectivity-amp-connectors/282834-8/1150136
    1   https://www.digikey.com/en/products/detail/sullins-connector-solutions/PRPC040SBAN-M71RC/2775294
        Or similar, everyone carries this
    2   https://www.polycase.com/screws-007-50
        Screws for mounting the PCB to the enclosure. The screws that come with are different, but might work.
    Hardware for mounting the TO-220 packages, totally optional


For PFET shutoff (as in the paper), solder Q1 and R11, omit R15.
For wake-on-INT, solder R15, omit Q1 and R11, jump pins 2 and 3 of Q1.


Comments
    Flip uC around so we can access the USB port
    Use 150mil screw terminals
        Can I find one with an angle, so they can be installed while it's in the box?
        https://www.mouser.com/ProductDetail/Wurth-Elektronik/691412320008?qs=lBTPRtX1sU%2FiaSubLXxkUg%3D%3D
        https://www.mouser.com/ProductDetail/Wurth-Elektronik/691412320002?qs=lBTPRtX1sU8RrNs89OcR%252BA%3D%3D


Ok, for real, BOM additions
2   https://www.mouser.com/ProductDetail/Wurth-Elektronik/691412320008?qs=lBTPRtX1sU%2FiaSubLXxkUg%3D%3D
1   https://www.mouser.com/ProductDetail/Wurth-Elektronik/691412320004?qs=lBTPRtX1sU9B2%2FymCxYonQ%3D%3D
1   https://www.digikey.com/en/products/detail/sullins-connector-solutions/PRPC040SBAN-M71RC/2775294 or anything like it from any seller
1   https://www.polycase.com/screws-007-50