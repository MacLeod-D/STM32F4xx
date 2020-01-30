This project uses CoopOS "classic" - no stackframes<br>
Another version with CoopOS_Stack (each Task has its own Stack) is running.<br>
Will be published soon.

# STM32F407 - Some Tests with RTOS / CoopOS, DAC, InputCapture 
## Running RTOS or CoopOS
## > 750000 External Interrupts / s
## > 750000 DA Conversions / s
## > 50000 Task Switches / s (RTOS and CoopOS)
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

-----------
## BTW: Task Switches

A lot of people think, an RTOS with a ticktime of 1ms will change to the (READY-)task with highest priority ever 1 ms.

**That is not true !**

Most RTOS Tasks have a TaskYIELD(), vTaskDelay() or a "wait for something" inside. And that means the tasks give up their CPU time very frequently! You will find tasks, which use the full 1 ms time, not very often !
So it could be very important to analyse how long the longest gap is between task switches.
Mostly this gap is much smaller than 1 ms.
If this gap is for instance garanteed smaller than 100 us then you can say, that a READY task never has to wait longer than 100 us for its execution - even if the ticktime is 1 ms.

** This time may be very important !

Here I show how to measure this time gap.

-----------

**Requisits:**

1) Arduino-IDE 1.8.10

2) Boards Definition:     https://github.com/danieleff/STM32GENERIC
                          It includes **freeRTOS** library
3) Toolchain as mentioned in 2)

4) Unzip **STM32F4_Timer1_InputCaptureISR_BU4.zip** into your Arduino Sketches folder 

5) STM32F407VE (Black Board)

6) USB-FTDI to connect Board to PC

7) Scope and/or Logic Analyser are highly recommended !
