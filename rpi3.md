# Raspberry Pi 3

I built ElectricSheep on RPi3 with Raspbian.

Basically, follow these instructions: https://github.com/scottdraves/electricsheep/wiki/Compiling 

````
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install subversion autoconf libtool libgtk2.0-dev libgl1-mesa-dev libavcodec-dev libavformat-dev libswscale-dev liblua5.1-0-dev libcurl4-openssl-dev libxml2-dev libjpeg8-dev libgtop2-dev libboost-dev libboost-filesystem-dev libboost-thread-dev libtinyxml-dev freeglut3-dev glee-dev

sudo apt-get install libwxbase31-0-unofficial
cd wxWidgets-3.1.0
./configure
make
sudo make install
cd

git clone https://github.com/scottdraves/flam3.git
cd flam3
./configure
make
sudo make install
cd

git clone https://github.com/scottdraves/electricsheep.git
cd electricsheep
cd client_generic
./autogen.sh
./configure
make
sudo make install
````

You should now have everything that you need. RPi3 does get hot with default settings. I do the following:

````
cd ~/.electricsheep
vim ElectricSheep.cf
````
and 

adjust cpuusagethreshold, player_fps, display_fps

I use

````
["cpuusagethreshold"]=25
["player_fps"]=10
["display_fps"]=10
````

and then run it

````
$ electricsheep
````



