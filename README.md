# Arduino Plugin for [Proffieboard](https://fredrik.hubbe.net/lightsaber/v4/)

This core retains the support for boards from the Arduino STM32L4 core that it is based on.

## Installing

### Board Manager

 1. [Download and install the Arduino IDE](https://www.arduino.cc/en/Main/Software) (at least version v1.6.8)
 2. Start the Arduino IDE
 3. Go into Preferences
 4. Add ```https://profezzorn.github.io/arduino-proffieboard/package_proffieboard_index.json``` as an "Additional Board Manager URL"
 5. Open the Boards Manager from the Tools -> Board menu and install "Proffieboard Plugin"
 6. Select Proffieboard Tools -> Board menu

#### OS Specific Setup

##### Linux

 1. Go to ~/.arduino15/packages/profezzorn/hardware/stm32l4/```<VERSION>```/drivers/linux/
 2. sudo cp *.rules /etc/udev/rules.d
 3. reboot

#####  Windows

###### STM32 BOOTLOADER driver setup for STM32L4 based boards

 1. Download [Zadig](http://zadig.akeo.ie)
 2. Plugin STM32L4 board and toggle the RESET button while holding down the BOOT button
 3. Let Windows finish searching for drivers
 4. Start ```Zadig```
 5. Select ```Options -> List All Devices```
 6. Select ```STM32 BOOTLOADER``` from the device dropdown
 7. Select ```WinUSB (v6.1.7600.16385)``` as new driver
 8. Click ```Replace Driver```

###### USB Serial driver setup for STM32L4 based boards (Window XP / Windows 7 only)

 1. Go to ~/AppData/Local/Arduino15/packages/profezzorn/hardware/stm32l4/```<VERSION>```/drivers/windows
 2. Right-click on ```dpinst_x86.exe``` (32 bit Windows) or ```dpinst_amd64.exe``` (64 bit Windows) and select ```Run as administrator```
 3. Click on ```Install this driver software anyway``` at the ```Windows Security``` popup as the driver is unsigned

### From git (for core development)

 1. Follow steps from Board Manager section above
 2. ```cd <SKETCHBOOK>```, where ```<SKETCHBOOK>``` is your Arduino Sketch folder:
  * OS X: ```~/Documents/Arduino```
  * Linux: ```~/Arduino```
  * Windows: ```~/Documents/Arduino```
 3. Create a folder named ```hardware```, if it does not exist, and change directories to it
 4. Clone this repo: ```git clone https://github.com/profezzorn/arduino-proffieboard.git profezzorn/stm32l4```
 5. Restart the Arduino IDE

## Recovering from a broken upload

 Sometimes a faulty sketch can render the normal USB Serial based integration into the Arduindo IDE not working. In this case plugin the STM32L4 board and toggle the RESET button while holding down the BOOT button and program a known to be working sketch to go ack to a working USB Serial setup.

## Credits

This core is based on the [Arduino STM32L4 Core](https://github.com/GrumpyOldPizza/arduino-STM32L4)

