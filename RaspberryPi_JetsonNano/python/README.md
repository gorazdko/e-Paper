## Abstract

Running LifeHash on GxEPD2 1.54 V2 with Raspberry pi 3.

* Connect your Rpi3 with your display:
  * [schematic RPI](https://docs.microsoft.com/en-us/windows/iot-core/media/pinmappingsrpi/rp2_pinout.png)
  * [schamatic Waveshare](https://www.waveshare.com/wiki/1.54inch_e-Paper_Module)

* Enable SPI on your [Rpi](https://www.raspberrypi-spy.co.uk/2014/08/enabling-the-spi-interface-on-the-raspberry-pi/)

* Clone the repo: `https://github.com/gorazdko/e-Paper.git`

* Run the example in `e-Paper/RaspberryPi_JetsonNano/python/examples` with:


```python
python a.py
```
This example will draw rgb data obtained from https://github.com/BlockchainCommons/bc-lifehash which you can run on Rpi
if you have the necessary [toolchain](https://solarianprogrammer.com/2017/12/08/raspberry-pi-raspbian-install-gcc-compile-cpp-17-programs/)

```cpp
auto image = LifeHash::make_from_utf8("some random string", Version::version2, 1);
```


![IMG_20210215_151210](https://user-images.githubusercontent.com/25270775/107982982-53cb3980-6fc5-11eb-8f95-b6cec4c4d185.jpg)

![IMG_20210215_150607](https://user-images.githubusercontent.com/25270775/107984478-4c595f80-6fc8-11eb-81e3-0a21ae0c86ec.jpg)


----

LifeHash modules were pre-generated with the following script:

```python


import numpy as np
from PIL import Image
import random

# Generate LifeHash modules of 6x6

# source: Victor Ostromoukhov: Halftoning by Rotating Non-Bayer Dispersed Dither Arrays
dither_array = [18, 30, 14, 17, 29, 13,    34, 2, 26, 33, 1, 25,    6, 22, 10, 5, 21, 9,      16, 28, 12, 19, 31, 15,    32, 0, 24, 35, 3, 27,    4, 20, 8, 7, 23, 11  ]

# generate 36 elements/shades
for i in range(0, 36):
    a = list(dither_array)
    for j in range(0, 36):
        if a[j] < i:
            a[j] = 0
        else:
            a[j] = 255
    na = np.array(a, dtype=np.uint8)
    im = Image.fromarray(na.reshape(6,6))
    im.save('shades_dithered/' + str(i) + '.bmp')
    
    ```

