# STM32F407 - Some Tests with RTOS / CoopOS, DAC, InputCapture 
## Running RTOS or CoopOS
## > 750000 External Interrupts / s
## > 750000 DA Conversions / s
## Use InputCapture for 6 ns Ticks
## Complete documented Source and 14 Page Explanation

There is a silent revolution:
The MCUs of today are so mighty. They will change our world within some years !

Small ESP8266 are VERY cheap today. ESP32 impresses with 2 indepentent cores.
Now I ordered 2 boards from China:

1) STM32F103 (bluepill) for amazing 1.79€ (including porto)
2) STM32F407 (blackboard) for       7.79€

Here are my first tests.

## !!! Please read   Comment.pdf   for more information !!!

**Requisits:**

1) Arduino-IDE 1.8.10

2) Boards Definition:     https://github.com/danieleff/STM32GENERIC
                          It includes **freeRTOS** library
3) Toolchain as mentioned in 2)

4) Unzip **STM32F4_Timer1_InputCaptureISR_BU4.zip** into your Arduino Sketches folder 

5) STM32F407VE (Black Board)

6) USB-FTDI to connect Board to PC

