# st7735fb
Frame buffer base st7735 lcd interface with raspberry PI

copy the prajst77.dts to you raspberry and build it using command below
dtc -@ -I dts -Odtc -@ -I dts -O dtb -o /boot/overlays/prajst77.dtbo prajst77.dts

The Reset Pin of LCD is connncted to GPIO 27 and Command/DC/AO is conncted to GPIO 25, you can directly connect the LED power to 3.3V of Raspberry PI
SPI 0 is used as SPI interface with GPIO 8 as Chip select


Open the /boot/config.txt and add below lines after spi=on and reboot once changes are added

dtoverlay=prajst77,debug=3


to check if Frambuffer is successfully added run command below

ls /dev/fb

if you see fb0 and fb1 then the frame buffer is added successfully and you all ready to go
