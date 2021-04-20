## Adafruit QT Py RP2040 PCB

<a href="http://www.adafruit.com/products/4900"><img src="assets/4900.jpg?raw=true" width="500px"><br/>
Click here to purchase one from the Adafruit shop</a>

PCB files for the Adafruit QT Py RP2040.

Format is EagleCAD schematic and board layout
* https://www.adafruit.com/product/4900

### Description

What a cutie pie! Or is it... a QT Py? This diminutive dev board comes with one of our new favorite chip, the RP2040. It's been made famous in the new Raspberry Pi Pico and our Feather RP2040 and ItsyBitsy RP2040, but what if we wanted something really smol?

A new chip means a new QT Py, and the Raspberry Pi RP2040 is no exception. When we saw this chip we thought "this chip is going to be awesome when we give it the cuuutie QT Py Treatment", and so we did! This QT Py features the RP2040, and all niceties you know and love about the original QT Py

#### Plug-and-play STEMMA QT

The star of the QT Py is our favorite connector - the STEMMA QT, a chainable I2C port that can be used with any of our STEMMA QT sensors and accessories. Having this connector means you don't need to do any soldering to get started.

What can you pop into the QT port? How about OLEDs! Inertial Measurment Units! Sensors a-plenty. All plug-and-play thanks to the innovative chainable design: SparkFun Qwiic-compatible STEMMA QT connectors for the I2C bus so you don't even need to solder. Just plug in a compatible cable and attach it to your MCU of choice, and you’re ready to load up some software and measure some light.

Use any SparkFun Qwiic boards! Seeed Grove I2C boards will also work with this adapter cable.

#### Software Support

At the time of launch, there is no Arduino core support for the chip on this board. There is great C/C++ support, an official MicroPython port, and a CircuitPython port! We of course recommend CircuitPython because we think it's the easiest way to get started and it has support with most of our drivers, displays, sensors, and more, supported out of the box so you can follow along with our CircuitPython projects and tutorials.

#### QT Py RP2040 Specifications

Pinout and shape is Seeed Xiao compatible, with castellated pads so you can solder it to a PCB with a cut out to allow the bottom components some breathing room. In addition to the QT connector, we also added an RGB NeoPixel (with a controllable power pin to allow for ultra-low-power usage), and both boot-mode and reset buttons (great for restarting your program or entering the bootloader). This QT Py comes with loose 0.1" headers you can solder in for breadboard use

While the RP2040 has lots of onboard RAM (264KB), it does not have built-in FLASH memory. Instead, that is provided by the external QSPI flash chip. On this board there is 8MB, which is shared between the program it's running and any file storage used by MicroPython or CircuitPython. When using C/C++ you get the whole flash memory, if using Python you will have about 7 MB remaining for code, files, images, fonts, etc.

* Same size, form-factor, and pin-out as our SAMD-based QT Py
* USB Type C connector - If you have only Micro B cables, this adapter will come in handy!
* RP2040 32-bit Cortex M0+ dual-core running at ~125 MHz @ 3.3V logic and power
* 264 KB RAM
* 8 MB SPI FLASH chip for storing files and CircuitPython/MicroPython code storage. No EEPROM
* Native USB supported by every OS - can be used as USB serial console, MIDI, Keyboard/Mouse HID, even a little disk drive for storing Python scripts.
* Can be used with MicroPython or CircuitPython
* Built-in RGB NeoPixel LED
* 13 GPIO pins (11 breakout pads and two QT pads):
  * Four 12 bit ADCs (one more than Pico)
  * Two I2C ports (one on the QT connector, one on the breakout pads)
  * SPI and UART peripherals, in standard QT Py locations,
  * PWM outputs on every IO pin - for servos, LEDs, etc
  * There are 6 GPIO in consecutive order for PIO compatibility
* 3.3V regulator with 600mA peak output
* 12 MHz crystal
* Both Reset button and Bootloader select buttons for quick restarts (no unplugging-replugging to relaunch code)
* Really really small

#### About the RP2040

Inside the RP2040 is a 'permanent ROM' USB UF2 bootloader. What that means is when you want to program new firmware, you can hold down the BOOT button while plugging it into USB (or pulling down the RUN/Reset pin to ground) and it will appear as a USB disk drive you can drag the firmware onto. Folks who have been using Adafruit products will find this very familiar - we use the technique on all our native-USB boards. Just note you don't double-click reset, instead hold down BOOTSEL during boot to enter the bootloader!

The RP2040 is a powerful chip, which has the clock speed of our M4 (SAMD51), and two cores that are equivalent to our M0 (SAMD21). Since it is an M0 chip, it does not have a floating point unit or DSP hardware support - so if you're doing something with heavy floating point math, it will be done in software and thus not as fast as an M4. For many other computational tasks, you'll get close-to-M4 speeds!

For peripherals, there are two I2C controllers, two SPI controllers, and two UARTs that are multiplexed across the GPIO - check the pinout for what pins can be set to which. There are 16 PWM channels, each pin has a channel it can be set to (ditto on the pinout).

You'll note there's no I2S peripheral, or SDIO, or camera, what's up with that? Well, instead of having specific hardware support for serial-data-like peripherals like these, the RP2040 comes with the PIO state machine system which is a unique and powerful way to create custom hardware logic and data processing blocks that run on their own without taking up a CPU. For example, NeoPixels - often we bitbang the timing-specific protocol for these LEDs. For the RP2040, we instead use PIO object that reads in the data buffer and clocks out the right bitstream with perfect accuracy. Same with I2S audio in or out, LED matrix displays, 8-bit or SPI based TFTs, even VGA! In MicroPython and CircuitPython you can create PIO control commands to script the peripheral and load it in at runtime. There are 2 PIO peripherals with 4 state machines each.

### License

Adafruit invests time and resources providing this open source design, please support Adafruit and open-source hardware by purchasing products from [Adafruit](https://www.adafruit.com)!

Designed by Limor Fried/Ladyada for Adafruit Industries.

Creative Commons Attribution/Share-Alike, all text above must be included in any redistribution.
See license.txt for additional details.
