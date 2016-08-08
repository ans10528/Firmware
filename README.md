## PX4 Pro Port for Erle-Brain2 ##

This repository holds the [PX4 Pro](http://px4.io) port for [Erle-Brain2](http://erlerobotics.com/blog/home-creative/).

### Use ###

1. because Erle-Brain2 is ARM archicture, to build px4 for it need download cross-compiler
   * `git clone https://github.com/pixhawk/rpi_toolchain.git`
   * `cd rpi_toolchain`
   * `./install_cross.sh`

2. make firmware:

	* 2.1 cmake version, only first time:

	   * `wget https://cmake.org/files/v3.4/cmake-3.4.3-Linux-x86_64.sh`
	   * `chmod +x cmake-3.4.3-Linux-x86_64.sh`
	   * `sudo mkdir /opt/cmake-3.4.3`
	   * `sudo ./cmake-3.4.3-Linux-x86_64.sh --prefix=/opt/cmake-3.4.3 --exclude-subdir`
* `export PATH=/opt/cmake-3.4.3/bin:$PATH`
* `make posix_erlebrain2_release` 

3. upload firmware though ssh 
   * On your computer: 

   		* `export AUTOPILOT_HOST=[ip]`
   		* `export AUTOPILOT_USER=erle`
   		* `make posix_erlebrain2_release upload`

4. before PX4 got run, it need create working directory.
	* On the Erle-Brain 2: 
   		* `mkdir -p /home/erle/px4/eeprom`
   		* `mkdir -p /home/erle/px4/fs`
5. run
   * `sudo ./mainapp`