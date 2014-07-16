Static Library Eclipse project for Arduino


### 1. Installing Eclipse

* check if you have java installed (and if tis on your PATH if you are using windows).
  by running java -version

* download eclipse with C++ deveopment tools  from
  http://www.eclipse.org/cdt/downloads.php
  and install it

missing: different achitectures, PATH, adding direct link to JVM in eclipse settings

Test: If you can start eclipse you can pass on


### 2. Installing Plugins and Toolchain

* Install the eclipse AVR Plugin via
    Help > Install News Software
  and by using
    http://avr-eclipse.sourceforge.net/updatesite



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

Install drivers
look up device by
  ls /dev | grep tty

### 5. Set up avr-dude

Create arduino as a device
use it in projects
