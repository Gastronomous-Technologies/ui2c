# ui2c - Arduino-based UART-to-I2C adapter 

Features:
 
* 3 protocols over USB UART (115200 8N1)
    * RAW (data length + address (1 or 2 bytes) and data itself, all in I2C bus format)
    * Coptonix #020101-like (Master mode)
    * manual: local echo, console commands, data in HEX, built-in bus scaner 
* 7/10 bit I2C address support
* data length up to 255 bytes
* python adapter class ui2c.py, implementing i2c_msg from smbus2.SMBus to simplify integration with 
    I2C/smbus applications and/or porting from Raspbery to Linux/Windows
* C/C++ API for integration with desktop applications under Linux/Windows
* build-in logging feature in RAW mode, doesn't interfere with regular data flow 

    
Origin: https://alter.org.ua/en/soft/arduino/ui2c/
uses WireZeroCopy I2C library (https://github.com/Alter-1/WireZeroCopy/)

# ui2c - Arduino-based UART-to-I2C adapter 

Features:
 
* 3 protocols over USB UART (115200 8N1)
    * RAW (data length + address (1 or 2 bytes) and data itself, all in I2C bus format)
    * Coptonix #020101-like (Master mode)
    * manual: local echo, console commands, data in HEX, built-in bus scaner 
* 7/10 bit I2C address support
* data length up to 255 bytes
* python adapter class ui2c.py, implementing i2c_msg from smbus2.SMBus to simplify integration with 
    I2C/smbus applications and/or porting from Raspbery to Linux/Windows
* C/C++ API for integration with desktop applications under Linux/Windows
* build-in logging feature in RAW mode, doesn't interfere with regular data flow 

    
Origin: https://alter.org.ua/en/soft/arduino/ui2c/
uses WireZeroCopy I2C library (https://github.com/Alter-1/WireZeroCopy/)

This fork adds three additional GPIO functions under the [I2C bus management section](https://alter.org.ua/en/soft/arduino/ui2c/).
Specifically: 

GPIO pin mode - **0xfc**  
0x01 0xff **0xfc** _pin_number_ _pin_mode_  
For pin mode:  
&emsp;0 - input  
&emsp;1 - output  
  
GPIO digital write - **0xfb**  
0x01 0xff **0xfb** _pin_number_ _pin_value_  
For pin value:  
&emsp;0 - low  
&emsp;1 - high  
  
GPIO digital read - **0xfa**   
0x01 0xff **0xfa** _pin_number_  
< _pin_value_  
