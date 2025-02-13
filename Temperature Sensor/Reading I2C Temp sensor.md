[ADT7420 Data Sheet](https://www.analog.com/media/en/technical-documentation/data-sheets/ADT7420.pdf)


## Hardware

The temperature is store in 2 registers (Addr 0x00 and 0x01). In default configuration, the sensor reads in 13bit mode, using the LSBs 0-2 as flag bits (T_crit, T_high, and T_low). Every bit after that is 0.0625deg C. The MSB is the sign bit.

Can be read with 2byte read, just need to set the address pointer reg to the most significant byte.

__Data Format Example__

| Tempurature (C) | Digital Output (Bits [15:3]) |
| --------------- | ---------------------------- |
| 0               | 0000 0000 0000 0_ _ _        |
| 0.0625          | 0000 0000 0000 1_ _ _        |
| -0.0625         | 1111 1111 1111 1_ _ _        |
| 25              | 0000 1100 1000 0_ _ _        |

Format can be configured using configuration register (will leave as default for project)

### Conversion Formula (13bit)

Positive Temp = ADC Code (dec) / 16
Negative Temp = (ADC Code (dec) - 8192) / 16


### Serial Bus Addr

Iic devices usually have a serial address used for comminication. The temp sensor has 4 options, with the A750T board hardwiring the address to be 0x4B.


## Questions

- How to join two byte numbers into one decimal?
	- Big brain, multiply MSB by $2^{shift}$  (so for 13 bit read, need to shift by 5 bits cause of the 3 LSbs being used for flags, so MSB * 2^5). Add that amount to the LSB. Profit
