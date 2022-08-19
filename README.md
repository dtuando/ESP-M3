# ESP-M3

![Pinout](https://arduinodiy.files.wordpress.com/2019/08/esp8285-m3.jpg)


PIN |     Function         |   Restrictions                                |  CAN USE FOR
-----------------------------------------------------------------------------------------------
0   | Boot mode select     |  Can't be used as an input.                   | FLASHING
    |                      |  State during boot is dependent on boot mode. |
-----------------------------------------------------------------------------------------------
1   | TX0                  |  During boot, debug is output on this pin.    |  SDA
-----------------------------------------------------------------------------------------------
2   | Boot mode select/TX1 |  Can't be used as an input. There is an       | ?
    |                      |  external pull-up on this pin, so it also     |
    |                      |  can't be used for applications that require  |
    |                      |  Hi-Z (such as I2C).                          |
-----------------------------------------------------------------------------------------------
3   | RX0                  | During boot, while debug is being output on   | SCL
    |                      | GPIO1, this is held high. So, if we use GPIO1 | 
    |                      | as SDA and this as SCL, no data will make it  | 
    |                      | to any slaves.                                |
-----------------------------------------------------------------------------------------------
4   | SDA                  | This is the default SDA pin, we moved I2C to  | IN/OUT
    |                      | GPIO1 and GPIO3 because it can handle the     |
    |                      | noise at boot, so it frees up this pin.       |
-----------------------------------------------------------------------------------------------                      
13  | MOSI                 | SPI Master out/slave in                       | 	MOSI
-----------------------------------------------------------------------------------------------
14  | SCK                  | SPI clock                                     | 	SCK
-----------------------------------------------------------------------------------------------
16  | WAKE FROM SLEEP      | This is used by the deep-sleep mechanism,     |
                           | should we want to use it.                     |
-----------------------------------------------------------------------------------------------
EN  | EN                   | Enable / CH_PD                                |
-----------------------------------------------------------------------------------------------



