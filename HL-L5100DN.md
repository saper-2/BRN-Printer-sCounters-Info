## HL-L5100DN

This is a newest printer that I have (just bought it :grin:) so there is not much in counters values so for most I'll identify IDs names looking on
others printers.

### HL-L5100DN - brInfoCounter

**OID:** `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.10` (**brInfoCounter**)

**RAW:** `0001040000000906010400000006ffffffff`
```
Stream length: 18 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: 00 01 04 00 00 00 09 06 01 04 00 00 00 06 FF FF ••••••••••••••••
00000010: FF FF                                           ••
```
HTTP:
```
Node Information
	Model Name: Brother HL-L5100DN series
	Main Firmware Version: 1.15
	Sub1 Firmware Version: 1.07
	Memory Size: 256MB
Device Status
	Page Counter        : 9      [00 09] #00
Total Pages Printed
	Total           : 9pages [00 09] 
	  2-sided Print : 6      [00 06] #06
```
RAW data organized in segments:
```
#00   9 = 00.0104.00000009 – Total page counter
#06   6 = 06.0104.00000006 – Duplex unit page count
#padEnd = ffffffff
```

### HL-L5100DN - brInfoCoverage

**OID:** `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.18` (**brInfoCoverage**)

**RAW:** `00020231ffffffff`
```
Stream length: 8 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: 00 02 02 31 FF FF FF FF                         •••1••••
```
HTTP:
```
Device Status
	Average Coverage****: 2.49%  [02 31] #00 (2=0x02 integer, 49=0x31 decimal)
```
RAW data organized in segments:
```
#00   2 31 = 00.02.0231 - Average Coverage [0x02=integer, 0x31=decimal]
#padEnd    = ffffffff
```
Value at MSB byte contains integer part of number (`0`-`100`), LSB byte
contains decimal part (`.00` - `.99`) .

### HL-L5100DN - brInfoMaintenance

**OID**:` 1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.8` (**brInfoMaintenance**)

**RAW:**
```
63010400000001110104000000254101040000271031010400000001
6f0104000026ffffffacffffff81010400000064ffffff8601040000000f
670104000000016b0104000027105401040000000166010400000001
350104000000016a0104000027106c0104000027106d010400002710ffffffff
```
```
Stream length: 118 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: 63 01 04 00 00 00 01 11 01 04 00 00 00 25 41 01 c••••••••••••%A•
00000010: 04 00 00 27 10 31 01 04 00 00 00 01 6F 01 04 00 •••'•1••••••o•••
00000020: 00 26 FF FF FF AC FF FF FF 81 01 04 00 00 00 64 •&•••••••••••••d
00000030: FF FF FF 86 01 04 00 00 00 0F 67 01 04 00 00 00 ••••••••••g•••••
00000040: 01 6B 01 04 00 00 27 10 54 01 04 00 00 00 01 66 •k••••'•T••••••f
00000050: 01 04 00 00 00 01 35 01 04 00 00 00 01 6A 01 04 ••••••5••••••j••
00000060: 00 00 27 10 6C 01 04 00 00 27 10 6D 01 04 00 00 ••'•l••••'•m••••
00000070: 27 10 FF FF FF FF                               '•••••
```
HTTP:
```
Remaining Life
	Drum Unit*: 100%        [27 10] #41
	Fuser Unit: 199991pages [03 0D 37] (% of Life Remaining: 100% [27 10] #6B)
	Laser Unit: 199991pages [03 0D 37] (% of Life Remaining: 100% [27 10] #6A)
	Paper Feeding Kit MP: 49999pages [C3 4F]    (% of Life Remaining: 100% [27 10] #6C)
	Paper Feeding Kit 1: 99995pages  [01 86 9B] (% of Life Remaining: 100% [27 10] #6D)
	Toner**: 100% [27 10] /or/ [64] #81
```
RAW data organized in segments:
```
#63      1 = 63.0104.00000001                - ? drum status (1-ok, 2-ending soon, 3-need replace) ?
#11     37 = 11.0104.00000025                - Drum unit page count
#41  10000 = 41.0104.00002710                - Remaining life: drum unit (0.01%)
#31      1 = 31.0104.00000001                - ? like drum – toner status ?
#6F   9900 = 6f.0104.000026.ffffff.ac.ffffff - ? Remaining life: toner (in 0.01%)
#81    100 = 81.0104.00000064.ffffff         - Remaining life: toner (in 1%)
#86     15 = 86.0104.0000000f                - ? toner minimum warn level ?
#67      1 = 67.0104.00000001                - ?
#6B  10000 = 6b.0104.00002710                - Remaining life: Fuser unit (int 0.01%) /or/ laser?
#54      1 = 54.0104.00000001                - ?
#66      1 = 66.0104.00000001                - ?
#35      1 = 35.0104.00000001                - ?
#6A  10000 = 6a.0104.00002710                - Remaining life: Laser unit (int 0.01%) /or/ fuser?
#6C  10000 = 6c.0104.00002710                - Remaining life: Paper Feeding Kit MP (int 0.01%)
#6D  10000 = 6d.0104.00002710                - Remaining life: Paper Feeding Kit 1 (int 0.01%)
#padEnd = ffffffff
```

### HL-L5100DN - brInfoNextCare

**OID:** `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.11` (**brInfoNextCare**)

**RAW:**
```
ffffff
8201040000ffffffc32bffffff89010400030d377
3010400030d37ffffff8601040000ffffffc34f
7701040001ffffff86ffffff9bffffffff
```
```
Stream length: 60 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: FF FF FF 82 01 04 00 00 FF FF FF C3 2B FF FF FF ••••••••••••+•••
00000010: 89 01 04 00 03 0D 37 73 01 04 00 03 0D 37 FF FF ••••••7s•••••7••
00000020: FF 86 01 04 00 00 FF FF FF C3 4F 77 01 04 00 01 ••••••••••Ow••••
00000030: FF FF FF 86 FF FF FF 9B FF FF FF FF             ••••••••••••
```
HTTP:
```
Remaining Life
	Drum Unit*: 100%        [27 10] 
	Fuser Unit: 199991pages [03 0D 37] #89
	Laser Unit: 199991pages [03 0D 37] #73
	Paper Feeding Kit MP: 49999pages [C3 4F] #86
	Paper Feeding Kit 1: 99995pages  [01 86 9B] #77 
	Toner**: 100% [27 10]
```
RAW data organized in segments:
```
#pad        = ffffff
#82   49963 = 82.0104.0000.ffffff.c32b.ffffff  - Remaining life: Drum unit (pages)
#89  199991 = 89.0104.00030d37                 - Remaining life: fuser unit /or/ laser unit (pages)
#73  199991 = 73.0104.00030d37.ffffff          - Remaining life: laser unit /or/ fuser unit (pages)
#86   49999 = 86.0104.0000.ffffff.c34f         - Remaining life: PF Kit MP (pages)
#77   99995 = 77.0104.0001.ffffff.86.ffffff.9b - Remaining life: PF Kit 1 (pages)
#padEnd     = ffffffff
```

### HL-L5100DN - brInfoReplaceCount

**OID:** `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.20` (**brInfoReplaceCount**)

**RAW:**
```
ffffff820100ffffffa00100ffffff890100730100ffffff860100770100ffffffff
```
```
Stream length: 34 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: FF FF FF 82 01 00 FF FF FF A0 01 00 FF FF FF 89 ••••••••••••••••
00000010: 01 00 73 01 00 FF FF FF 86 01 00 77 01 00 FF FF ••s••••••••w••••
00000020: FF FF                                           ••
```
HTTP:
```
Replace Count
	Toner                : 0 [00] #A0
	Drum Unit            : 0 [00] #82
	Fuser Unit           : 0 [00] #89
	Laser Unit           : 0 [00] #73
	Paper Feeding Kit MP : 0 [00] #86
	Paper Feeding Kit 1  : 0 [00] #77
```
RAW data organized in segments:
```
#pad    = ffffff
#82   0 = 82.01.00.ffffff - Replace count: drum unit
#a0   0 = a0.01.00.ffffff - Replace count: toner
#89   0 = 89.01.00        - Replace count: fuser unit /or/ laser unit
#73   0 = 73.01.00.ffffff - Replace count: laser unit /or/ fuser unit
#86   0 = 86.01.00        - Replace count: PF Kit MP
#77   0 = 77.01.00        - Replace count: PF Kit 1
#padEnd = ffffffff
```

### HL-L5100DN - brInfoJamCount

**OID:** `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.21` (**brInfoJamCount**)

**RAW:**
```
0002000001020000210200002202000023020000ffffffa10400000000ffffffff
```
```
Stream length: 33 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: 00 02 00 00 01 02 00 00 21 02 00 00 22 02 00 00 ••••••••!•••"•••
00000010: 23 02 00 00 FF FF FF A1 04 00 00 00 00 FF FF FF #•••••••••••••••
00000020: FF                                              •
```
HTTP:
```
Total Paper Jams : 0 [00 00 00 00] #A0
	Jam MP Tray  : 0 [00 00] #00
	Jam Tray 1   : 0 [00 00] #01
	Jam Inside   : 0 [00 00] #21
	Jam Rear     : 0 [00 00] #22
	Jam 2-sided  : 0 [00 00] #23
```
RAW data organized in segments:
```
#00   0 = 00.02.0000        - Jam count: MP tray
#01   0 = 01.02.0000        - Jam count: Tray 1
#21   0 = 21.02.0000        - Jam count: inside
#22   0 = 22.02.0000        - Jam count: rear
#23   0 = 23.02.0000.ffffff - Jam count: duplex unit
#A1   0 = a1.04.00000000    - Total jam count
#padEnd = ffffffff
```