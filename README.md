# Response XE

Some notes and links:

[response](https://www.instructables.com/SMART-Response-XE-Tiny-Basic-Port/)

Microcontroller: At its core is the Atmel (Microchip) ATmega128RFA1 system-on-chip, which combines an AVR 8-bit microcontroller with an integrated 2.4 GHz ZigBee / IEEE 802.15.4 radio transceiver.

https://github.com/fdufnews/SMART-Response-XE-schematics/blob/master/Smart_Response_XE.pdf

https://github.com/chmod775/SMARTResponseTerminal

Arduino library for hardware:

https://github.com/bitbank2/SmartResponseXE

Steps for installing BASIC

https://www.instructables.com/SMART-Response-XE-Tiny-Basic-Port/

https://github.com/Subsystems-us/SMART-Response-XE-Tiny-Basic-Port

```
avrdude -c USBasp -p m128rfa1 -U flash:w:tiny_basic_SE_03.ino.hex:i -F -B 32

avrdude -c USBasp -p m128rfa1 -U flash:w:SMARTResponseTerminal.ino.rf128.hex:i -F -B 32
```

```
>>> import board
>>> import busio
>>> import time
>>>
>>> uart = busio.UART(board.GP0, board.GP1, baudrate=9600)
>>>
>>> uart.write(b"Hello World\n")
12
>>> uart.write(b"Hello World\n")
12
>>> while True:
...     data = uart.read(1)
...     if data:
...         print(data)
...     time.sleep(1)

```
