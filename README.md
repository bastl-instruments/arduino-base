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

  When the Eclipse plugin can locate those tools you were successful. You can check this in:
    Preferences > AVR > Paths
  The 'Atmel Part Description Files' are not needed here.


### 3. Set up Serial connector

* Install drivers for the programmer you are using to upload code to the chip.
  For the sparkfun FTDI, the drivers are included in the arduino IDE. If you have it installed, you are done with this step.
  In case have a different configuration, search for you FDTI chip on the web.

* Plug in your programmer and find out the serial port it is using.
  On mac on linux, this command will help you choose your device:
  ls /dev | grep tty
  
* Create an AVR programmer in Eclipse. Open
    Preferences > AVR > AVRDuded > Add
  Choose the following options:
    Programmer Hardware: Arduino
    Default port: //the path you found out in the last step//
    Default Baudrate: 115200





### 4. Create Workspace and Projects

* Choose a workspace directory. We will refer to it as W_DIR.

* Download the repositories from bastl-instruments and copy them in the following matter

	 `W_DIR<br/>
	  &nbsp;&nbsp;|<br/>
	  &nbsp;&nbsp; arduino_base<br/>
	  &nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;|<br/>
	  &nbsp;&nbsp;|&nbsp;&nbsp;libs-bastl<br/>
	  &nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;|<br/>
	  &nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;bastl<br/>
	  &nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;|<br/>
	  &nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;..other library repositories from bastl instruments<br/>
	  &nbsp;&nbsp;| <br/>
	  &nbsp;&nbsp;SEKVOJ<br/>
	  &nbsp;&nbsp;|<br/>
	  &nbsp;&nbsp;..other device specific projects`<br/>

* Import arduino-base and the device projects in Eclipse by right-clicking in the project explorer and choosing
    Import > Existing projects into workspace

* Add the programmer you created in the previous step to all projects (except for arduino-base because it is a library).
  Therefore go to:
    Right click on project
  







### Links
http://playground.arduino.cc/code/eclipse
