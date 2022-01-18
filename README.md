Open source libraries for STM32 development
===========================================

This is a collection of open source libraries I use frequently when developing software for STM32 microcontrollers. The purpose of this repository is to make an easy and convenient way of installing everything for myself. And also to give you an insight of what I use, and why I use it.

All libraries are added as git submodules from their original git repository.


### Todo

 * I do have some custom build scripts (using CMake) that I plan to put here as well
 * Add more useful projects
 * Maybe add more information about the projects


Libraries
---------

Library                    | Provider           | License
---------------------------|--------------------|--------------
[CMSIS Core](1)            | Arm                | Apache-2.0
[CMSIS Device](2)          | STMicroelectronics | Apache-2.0
[STM32 HAL & LL Driver](3) | STMicroelectronics | BSD-3-Clause
[newlib-cygwin](4)         |                    | Mixed
[FreeRTOS-Kernel](5)       |                    | MIT
[libusb](6)                |                    | LGPL-2.1
[lwip](7)                  |                    | Modified BSD License

[1]: https://github.com/ARM-software/CMSIS_5
[2]: https://github.com/STMicroelectronics/cmsis_device_f4
[3]: https://github.com/STMicroelectronics/stm32f4xx_hal_driver
[4]: https://sourceware.org/newlib/
[5]: https://www.freertos.org/
[6]: https://libusb.info/
[7]: https://savannah.nongnu.org/projects/lwip/



### CMSIS Version 5

The CMSIS is a set of tools, frameworks, API's, etc that basically works as a vendor-independent hardware abstraction layer for Arm Cortex processors. It also adds some other useful things like a software DSP library. This is provided by Arm and used indirectly or directly by most manufacutrers, libraries, etc. In my opinion this should probably be the base for any Arm Cortex based project.



### CMSIS Device

The CMSIS Device module implements preprocessor macros with mapping to all registers in a specified microcontroller. So if you want to access GPIOA on a STM32F405 you could just refer to GPIOA instead of it's memory mapped address 0x40020000.



### STM32 LL

LL stands for Low Level and is basically just a set of functions used to make it easier to modify the peripheral registers directly. Just as the name suggest, it is really low level, but still higher level than the CMSIS Device module.



### STM32 HAL

HAL stands for Hardware Abstraction Layer. This library makes it easy to run the same code on different microcontrollers within the same family, or even in different families. You could for example initialize an UART with the help of HAL. Then you wont need to mess around with registers and interrupts. HAL will do everything for you. I use HAL mostly as a reference to implement things manually with LL.



### newlib

A resource efficient implementation of [libc](https://en.wikipedia.org/wiki/C_standard_library) more suitable for microcontrollers. Does implement all the standard functions like memcpy(), sprintf(), etc.



### FreeRTOS

A free and popular realtime operating system for embedded devices.



### libusb

Open source USB stack



### lwIP

Open source TCP/IP stack
