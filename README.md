## PX4 Pro Port for Erle-Brain2 ##

This repository holds the [PX4 Pro](http://px4.io) port for [Erle-Brain2](http://erlerobotics.com/blog/home-creative/).

### Use ###

1. because Erle-Brain2 is ARM archicture, to build px4 for it need download cross-compiler
   git clone https://github.com/pixhawk/rpi_toolchain.git
   cd rpi_toolchain
   ./install_cross.sh

2. make firmware
   make posix-erlebrain2-release 

3. upload firmware though ssh 
   export AUTOPILOT_HOST=[ip]
   export AUTOPILOT_USER=erle
   make posix-erlebrain2-release upload

4. before PX4 got run, it need create working directory.
   mkdir -p /home/erle/px4/eeprom
   mkdir -p /home/erle/px4/fs
5. run
   sudo ./mainapp erlebrain2.config

Enjoy!