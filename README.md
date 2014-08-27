Static Library Eclipse project for Arduino


### 1. Installing Eclipse

* check if you have java installed (and if tis on your PATH if you are using windows).
  by running java -version

* download eclipse with C++ deveopment tools  from
  http://www.eclipse.org/cdt/downloads.php
  and install it

missing: different achitectures, PATH, adding direct link to JVM in eclipse settings

Test: If you can start eclipse you can pass on


### 2. Installing Eclipse Plugins and Toolchain

* Eclipse-PLUGIN
  Open Eclipse and go to
    Help > Install News Software
  There, paste this link
    http://avr-eclipse.sourceforge.net/updatesite
  into the first field called 'Work with'

  Click through the install process.
  If you want to check if the installation was successful, go to
    Help > About Eclipse Platform > Installation Details
  and look for the AVR plugin

* AVR TOOLCHAIN
  You will need to install the avr-g++ compiler in order to compile your code to a .hex file and send it to the chip over your serial port.
  This step depends on your platform:
  - MAC OSX: Download and install the AVR CrossPack: http://www.obdev.at/products/crosspack/index.html
  - Linux: sudo apt-get install gcc-avr binutils-avr avr-libc avrdude
  - Windows: Download and install WinAVR: http://winavr.sourceforge.net/




### 3. Create Workspace and Projects

* Choose a workspace directory. We will refer to it as W_DIR.

* Download the repositories from bastl-instruments and copy them in the following matter

 `W_DIR
    |
    arduino_base
    |   |
    |   libs-bastl
    |       |
    |	    bastl
    |       |
    |       ..other library repositories from bastl instruments
    | 
    SEKVOJ
    |
    ..other device specific projects`

* Import arduino-base and the device projects in Eclipse by right-clicking in the project explorer and choosing
    Import > Existing projects into workspace

### 4. Set up Serial connector

* Install drivers for the programmer you are using to upload code to the chip
  
look up device by
  ls /dev | grep tty

### 5. Set up avr-dude

Create arduino as a device
use it in projects
