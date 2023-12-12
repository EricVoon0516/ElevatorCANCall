# STEP COP Protocol (HJ Analysis) Version 2.5
> `Data[]` consists of 8 bytes of data. **Null are those unlisted ?Data[0-7] in the table.**

## Activate SM.02 G and Beeping
| ID 	| Data[0] | Data[1] | Data[2] | Data[4] |
|:-----:|:----:|:----:|:--------------------------------:|:--------------------:|
| 0x008 | 0x04 | 0x0A | Bit6 : Long beep Bit7: Fast beep | customer code = 0x75 |

## Car call button light output signal
|| ID | Data[0] | Data[1] | Data[2] | Data[3] | Data[4] | Data[5] | Data[6] | Data[7] |
|:---------------:|:-----:|:----:|:----:|:-------:|:-------:|:-------:|:-------:|:-------:|:-------:|
| **Floor 1 - 48** ||||||||||
| master COP      | 0x008 | 0x03 | 0x0A | 8 - 1 | 16 - 9 | 24 - 17 | 32 - 25 | 40 - 33 | 48 - 41 |
| rear door COP   | 0x008 | 0x07 | 0x0A | 8 - 1 | 16 - 9 | 24 - 17 | 32 - 25 | 40 - 33 | 48 - 41 |
| handicapped COP | 0x008 | 0x08 | 0x0A | 8 - 1 | 16 - 9 | 24 - 17 | 32 - 25 | 40 - 33 | 48 - 41 |
| slave COP       | 0x008 | 0x09 | 0x0A | 8 - 1 | 16 - 9 | 24 - 17 | 32 - 25 | 40 - 33 | 48 - 41 |
| ...             | ...   | ...  | ...  | ...   | ...    | ...     | ...     | ...     | ...     |
|**Floor 49 - 96**  ||||||||||
| master COP      | 0x008 | 0x0B | 0x0A | 56 - 49 | 64 - 57 | 72 - 65 | 80 - 73 | 88 - 81 | 96 - 89 |
| rear door COP   | 0x008 | 0x0C | 0x0A | 56 - 49 | 64 - 57 | 72 - 65 | 80 - 73 | 88 - 81 | 96 - 89 |
| handicapped COP | 0x008 | 0x0F | 0x0A | 56 - 49 | 64 - 57 | 72 - 65 | 80 - 73 | 88 - 81 | 96 - 89 |
| slave COP       | 0x008 | 0x10 | 0x0A | 56 - 49 | 64 - 57 | 72 - 65 | 80 - 73 | 88 - 81 | 96 - 89 |

## Car door button light output signal
|| ID | Data[0] | Data[1] | Data[2]|
|:------:|:------:|:------:|:------:|:------:|
| master COP | 0x008 | Bit0 : door open <br/> Bit1 : door close | 0x83 | SM09 OUTPUT / BES CAR 4 <br/> Bit0 : JP6.1    / JP9.1 <br/> Bit1 : JP6.2    / JP9.2 <br/> Bit2 : JP6.3    / JP9.3 <br/> Bit3 : JP7.1    / JP6.1 <br/> Bit4 : JP8.1    / JP7.1 <br/> Bit5 : JP9.1    / JP8.1 <br/> Bit6 : LED D21 <br/> Bit7 : | 
| rear door COP | 0x008 | Bit0 : door open <br/> Bit1 : door close | 0x84 | SM09 OUTPUT / BES CAR 4 <br/> Bit0 : JP6.1    / JP9.1 <br/> Bit1 : JP6.2    / JP9.2 <br/> Bit2 : JP6.3    / JP9.3 <br/> Bit3 : JP7.1    / JP6.1 <br/> Bit4 : JP8.1    / JP7.1 <br/> Bit5 : JP9.1    / JP8.1 <br/> Bit6 : LED D21 <br/> Bit7 : |
| handicapped COP | 0x008 | Bit0 : door open <br/> Bit1 : door close | 0x85 | SM09 OUTPUT / BES CAR 4 <br/> Bit0 : JP6.1    / JP9.1 <br/> Bit1 : JP6.2    / JP9.2 <br/> Bit2 : JP6.3    / JP9.3 <br/> Bit3 : JP7.1    / JP6.1 <br/> Bit4 : JP8.1    / JP7.1 <br/> Bit5 : JP9.1    / JP8.1 <br/> Bit6 : LED D21 <br/> Bit7 : | 
| slave COP | 0x008 | Bit0 : door open <br/> Bit1 : door close | 0x86 | SM09 OUTPUT / BES CAR 4 <br/> Bit0 : JP6.1    / JP9.1 <br/> Bit1 : JP6.2    / JP9.2 <br/> Bit2 : JP6.3    / JP9.3 <br/> Bit3 : JP7.1    / JP6.1 <br/> Bit4 : JP8.1    / JP7.1 <br/> Bit5 : JP9.1    / JP8.1 <br/> Bit6 : LED D21 <br/> Bit7 : | 
||||||
||||||
|**Data[4]**| Bit5 : Floor button beep enabled |


## Function input signal / Car door button input signal
| ID | ID | DATA | DATA | DATA | DATA | DATA | DATA | DATA | DATA |
|:---------------:|:-----:|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:----:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:----:|:----:|:----:|:----:|:----:|
| ID | ID | D[0] | D[1] | D[2] | D[3] | D[4] | D[5] | D[6] | D[7] |
| master COP | 0x00A | Bit0 : JP5.1 Input GX0 attendant reversion
Bit1 : JP5.2 Input GX1 attendant
Bit2 : JP5.3 Input GX2 independent
Bit3 : JP5.4 Input GX3 attendant bypass
Bit4 : JP5.5 Input GX4 fireman
Bit5 : JP6 GX5 door opening button
Bit6 : JP7 GX6 door closed button
Bit7 : | 0x7E | SM09 INPUT / BES CAR 4
Bit0 : JP3.1  / JP10.1 
Bit1 : JP3.2  / JP10.2
Bit2 : JP3.3  / JP10.3
Bit3 : JP4.1  / JP11.1
Bit4 : JP4.2  / JP11.2
Bit5 : JP5.1  / JP12.1
Bit6 : 
Bit7 : |  |  |  |  |  |
| rear door COP | 0x00B | Bit0 : JP5.1 Input GX0 attendant reversion
Bit1 : JP5.2 Input GX1 attendant
Bit2 : JP5.3 Input GX2 independent
Bit3 : JP5.4 Input GX3 attendant bypass
Bit4 : JP5.5 Input GX4 fireman
Bit5 : JP6 GX5 door opening button
Bit6 : JP7 GX6 door closed button
Bit7 : | 0x7F | SM09 INPUT / BES CAR 4
Bit0 : JP3.1  / JP10.1 
Bit1 : JP3.2  / JP10.2
Bit2 : JP3.3  / JP10.3
Bit3 : JP4.1  / JP11.1
Bit4 : JP4.2  / JP11.2
Bit5 : JP5.1  / JP12.1
Bit6 : 
Bit7 : |  |  |  |  |  |
| handicapped COP | 0x00C | Bit0 : JP5.1 Input GX0 attendant reversion
Bit1 : JP5.2 Input GX1 attendant
Bit2 : JP5.3 Input GX2 independent
Bit3 : JP5.4 Input GX3 attendant bypass
Bit4 : JP5.5 Input GX4 fireman
Bit5 : JP6 GX5 door opening button
Bit6 : JP7 GX6 door closed button
Bit7 : | 0x80 | SM09 INPUT / BES CAR 4
Bit0 : JP3.1  / JP10.1 
Bit1 : JP3.2  / JP10.2
Bit2 : JP3.3  / JP10.3
Bit3 : JP4.1  / JP11.1
Bit4 : JP4.2  / JP11.2
Bit5 : JP5.1  / JP12.1
Bit6 : 
Bit7 : |  |  |  |  |  |
| slave COP | 0x00D | Bit0 : JP5.1 Input GX0 attendant reversion
Bit1 : JP5.2 Input GX1 attendant
Bit2 : JP5.3 Input GX2 independent
Bit3 : JP5.4 Input GX3 attendant bypass
Bit4 : JP5.5 Input GX4 fireman
Bit5 : JP6 GX5 door opening button
Bit6 : JP7 GX6 door closed button
Bit7 : | 0x81 | SM09 INPUT / BES CAR 4
Bit0 : JP3.1  / JP10.1 
Bit1 : JP3.2  / JP10.2
Bit2 : JP3.3  / JP10.3
Bit3 : JP4.1  / JP11.1
Bit4 : JP4.2  / JP11.2
Bit5 : JP5.1  / JP12.1
Bit6 : 
Bit7 : |  |  |  |  |  |

## Car call button input signals
| ID | ID | Data[0] | Data[1] | Data[2] | Data[3] | Data[4] <br/> - <br/> Data[7] | 
|:---------------:|:-----:|:-----------------------------------------------:|:----:|:---------------------------------------:|:--------------------:|:----:|
| master COP | 0x00A | 0x01 = release to press <br/> 0x00 = press to release | 0x6E | N floor car call button N = 0x01 ~ 0x60 | customer code = 0x75 |  |   
| rear door COP | 0x00B | 0x01 = release to press <br/> 0x00 = press to release | 0x6F | N floor car call button N = 0x01 ~ 0x60 | customer code = 0x75 |  | 
| handicapped COP | 0x00C | 0x01 = release to press <br/> 0x00 = press to release | 0x70 | N floor car call button N = 0x01 ~ 0x60 | customer code = 0x75 |  |
| slave COP | 0x00D | 0x01 = release to press <br/> 0x00 = press to release | 0x71 | N floor car call button N = 0x01 ~ 0x60 | customer code = 0x75 |  | 

