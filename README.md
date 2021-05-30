
![R3DUX](https://github.com/Kekule-OXC/R3DUX/blob/main/images/redux.JPG?raw=true)

![R3DUX board](https://github.com/Kekule-OXC/R3DUX/blob/main/Hardware/R3DUX%20bottom.JPG?raw=true)

## About this Repository
This is an open source recreation of one of the most well known Original Xbox LPC memory/IO device created by Team Xecuter, the X3/X3-CE.

The VHDL is 100% compatible with All the original TX software including Flashbios and LiveConfig. This allows loading user BIOS binaries and some basic Xbox tools (EEPROM Backup/modification, Hard drive Rebuilding, Locking, Unlocking, FTP access, as well as customizing the colors of the boot animation).  
  
The VHDL written by Team Xecuter was never released and the CPLD is read protected so it is not trivial to extract the bitstream (and they mislabelled the CPLD to make it even more difficult)

While the VHDL is most likely quite different that what was written originally for the X3 my VHDL implementation is fully compatible with all the features of the original chip.
## Background
The R3DUX chip started off as the OpenX3 project in January 2020 with four members of the discussion group for the RE effort, myself (Kekule)  [Team-Donkey](https://github.com/bolwire),  [Ryzee119](https://github.com/Ryzee119),  and [Ernegien](https://github.com/Ernegien).  

We worked for several months and KingLuxor and I completed a schematic based on the original purple X3 chip ([which he released in 2020](https://github.com/bolwire/OpenX3_Public))  with all of their help we identified the components of the PCB and, KingLuxor did the initial part placement, and I did the PCB layout of our initial OpenX3 chip.  

After verifying that the PCB worked (by transplanting all components from a working X3 chip)  the world was hit by the pandemic, and COVID and real life caused the project to fall aside.    

Ergenien was able to extract the majority of the register information need to complete the design, but the real life time demands of virtual work and school there was no time to even start working on the CPLD code.  
 
Time passed and we all went our separate ways, and so with a known working PCB in hand, and a trove of information we had amassed, the project was abandoned.

Fast forward about six months and I decided to start working on it again, and breathed new life into the project, a REDUX as it were.


## Supported Features

R3DUX Features: 

* Purple board color
* Comes from pre-flashed with FlashBIOS utility
* 2MB Flash ROM; can set up 8x256k, 4x512k, 2x1024k or a single 2048k banks
* Dedicated 256k Backup Rom (can be upgraded) 
* i2c Bus for X3 Config LIVE interface to the EEPROM! 
* I/O Bus for Full LCD support 
* Flash Protection Control 
* Mod Enable - Quick Press Power to boot from 2Mb Flash Rom (External LED will indicate BLUE LED) 
* Mod Disable - Press Power >1 second (External LED will indicate RED LED) 
* Quick Press Power+Eject >1 second to boot from 256k Backup Rom (External LED will indicate PURPLE LED) 
* HDD and LAN Activity LEDs
* D0 Control (Disable Mod Via Software) 
* R3DUX works without any switch accessories connected (boots to the first 1MB bank)
* Compatible with all BIOSes 

LCD-Specific Features:
* Custom text Display on boot 
* Display X3 Config Live Version 
* Display Dip switch and selected BIOS
* XBMC and Avalaunch LCD features are compatible

A mix of features from the purple and CE editions
* XLCD connector is a right angle instead of straight
* Single Pinheader for 5v connection on a v1.6 xbox




## Installation and Initial Setup
Installation is identical to an OEM X3 chip, and all connections are fully compatible so can be used plug and play with a previous X3 install.
 
See [Installation.MD] for more details

## Licensing
R3DUX gerbers and schematic are free and open source. Please respect the licenses available in their respective folders.
  *  Hardware is shared under the [CERN OHL version 1.2.](https://ohwr.org/cernohl).
  *  Firmware is shared under [GPLv3](https://www.gnu.org/licenses/quick-guide-gplv3.en.html).
 
## References that helped me in this project
  * [Intel LPC Spec](https://www.intel.com/content/dam/www/program/design/us/en/documents/low-pin-count-interface-specification.pdf)
  * [LPC Analyser Plugin](https://github.com/Ryzee119/LPCAnalyzer)  
  * [Deconstructing the Xbox Boot ROM](https://mborgerson.com/deconstructing-the-xbox-boot-rom/)

By Kekule
