# compile-wiringPi-to-openwrt
Compile [wiringPi](https://github.com/WiringPi/WiringPi) ipks by openwrt for raspberry Pi.



1. Put those dirs under package/utils.
2. `make menuconfig` and choice wiringPiGPIO.
3. compile wiringPiGPIO by `make package/wiringPiGPIO/compile`
4. copy libwiringPi_xxx.ipk,libwiringPiDev_xxx.ipk and wiringPiGPIO_xxx.ipk to raspberryPi.
5. install them by `opkg install xxxx.ipk`







