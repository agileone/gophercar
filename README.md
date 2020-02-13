# Gophercar

![Gophercar FPV](https://github.com/hybridgroup/gophercar/blob/master/images/gophercar-fpv.gif?raw=true)

Gophercar is a DIY platform for self-driving miniature cars like Donkeycar ([http://www.donkeycar.com/](http://www.donkeycar.com/)), but is written in the Go programming language. The idea is to make Gophercar able to run on any of the supported Donkeycar cars/hardware without any modification.

## How it works

![Arch](https://github.com/hybridgroup/gophercar/blob/master/images/arch.png?raw=true)

## Car and Controller Hardware

- Hobby King Rattler (ESC + rf radio)
- Beagleboard Blue
- Logitech C270 web camera
- NO PCA9685 I2C servo driver (included in Donkeycar kit)
- no SSD1306 I2C OLED display (optional)
- no MPU6050 I2C Accelerometer/Gyroscope (optional)

## Car OS Software

The following needs to be installed on a bootable SD card for the BBlue:

- Debian 9.0 OS image (https://debian.beagleboard.org/images/bone-debian-9.9-lxqt-armhf-2019-08-03-4gb.img.xz)
- Go v1.10+
- OpenCV 3.4.2
- SDL2 v2.0.8+

The following OS features must be enabled:

- I2C
- Camera

You will also need to update the kernel on the Raspbian Pi to v4.14+

    sudo rpi-update

## Current workflow

- Edit your car in a sub-directory of the `cars` directory.
- To transfer your code to the car, compile it on the car, and then run it:
    ./runner.sh hello 192.168.1.42

This copies the code to the BBlue, compiles it on the BBlue, and then executes it.

## Future workflow

- Install the Gophercar Docker container to cross-compiling for Raspian easier, due to using binary libaries such as OpenCV/GoCV
- Compile the code to run on your car
- Copy the compiled executable to your car's controller using scp
- Execute the car code on the car controller
- Drive!

## Cars

The `cars` directory will contain various car controller programs. Choose one to compile and put on your car controller.

![Gophercon 2018](https://github.com/hybridgroup/gophercar/blob/master/images/gophercon2018.gif?raw=true)
