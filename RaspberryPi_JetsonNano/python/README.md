## Abstract

Running LifeHash on GxEPD2 1.54 V2 with Raspberry pi 3.


* Make sure you have the necessary [toolchain on your Rpi](https://solarianprogrammer.com/2017/12/08/raspberry-pi-raspbian-install-gcc-compile-cpp-17-programs/)

* Connect your Rpi3 with your display:
  * [schematic RPI](https://docs.microsoft.com/en-us/windows/iot-core/media/pinmappingsrpi/rp2_pinout.png)
  * [schamatic Waveshare](https://www.waveshare.com/wiki/1.54inch_e-Paper_Module)

* Enable SPI on your [Rpi](https://www.raspberrypi-spy.co.uk/2014/08/enabling-the-spi-interface-on-the-raspberry-pi/)

* Clone the repo: `https://github.com/gorazdko/e-Paper.git`

* Run the example in `e-Paper/RaspberryPi_JetsonNano/python/examples` with:


```python
python a.py
```


![IMG_20210215_151210](https://user-images.githubusercontent.com/25270775/107982982-53cb3980-6fc5-11eb-8f95-b6cec4c4d185.jpg)
