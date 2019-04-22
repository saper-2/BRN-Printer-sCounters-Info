## MFC-8880DN

This is oldest printer that I have, it use older web UI, like DCP-7065
it have brInfoCounter record value split in half by 3xFF separator.

### MFC-8880DN - brInfoCounter

**OID:** `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.10` (**brInfoCounter**)

**RAW:** `0001040002ffffffde53ffffffff`
```
Stream length: 14 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: 00 01 04 00 02 FF FF FF DE 53 FF FF FF FF       •••••••••S••••
```
HTTP:
```
Node Information
    Model Name           : Brother MFC-8880DN
    Firmware Version     : Q
    Sub Firmware Version : 1.03
    Memory Size          : 64 Mbytes
Device Status
    Page Counter  : 187987 [02 DE 53] #00
    Drum Count    : 3967   [0F 7F]
```
RAW data organized in segments:
```
#00  187987 = 00.0104.0002.ffffff.de53 – Page counter
#padEnd     = ffffffff
```

### MFC-8880DN - brInfoMaintenance

**OID**: `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.8` (**brInfoMaintenance**)

**RAW:**
```
6301040000000111010400000f7f410104000021ffffff98
310104000000016f0104000016ffffffa867010400000001
6b010400001c20540104000000016601040000000135010400000003
6a010400001c206c0104000027106d010400000000ffffffff
```
```
Stream length: 101 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: 63 01 04 00 00 00 01 11 01 04 00 00 0F 7F 41 01 c•••••••••••••A•
00000010: 04 00 00 21 FF FF FF 98 31 01 04 00 00 00 01 6F •••!••••1••••••o
00000020: 01 04 00 00 16 FF FF FF A8 67 01 04 00 00 00 01 •••••••••g••••••
00000030: 6B 01 04 00 00 1C 20 54 01 04 00 00 00 01 66 01 k••••• T••••••f•
00000040: 04 00 00 00 01 35 01 04 00 00 00 03 6A 01 04 00 •••••5••••••j•••
00000050: 00 1C 20 6C 01 04 00 00 27 10 6D 01 04 00 00 00 •• l••••'•m•••••
00000060: 00 FF FF FF FF                                  •••••
```
**HTTP:**
```
Device Status
    Page Counter  : 187987 [02 DE 53]
    Drum Count    : 3967   [0F 7F] #11
Remaining Life
    Drum Unit*     21033 pages [52 29]    (% remaining 86.00% 86=[56] / 8600=[21 98] #41)
    Fuser Unit     71175 pages [01 16 07] (% remaining 72.00% 72=[48] / 7200=[1C 20] #6B)
    Laser Unit     71175 pages [01 16 07] (% remaining 72.00% 72=[48] / 7200=[1C 20] #6A)
    Paper Feeding Kit MP     49381 pages [C0 E5] (% remaining 100.00% 100=[64] / 10000=[27 10] #6C)
    Paper Feeding Kit 1     0 pages      [00 00] (% remaining   0.00%   0=[00] /     0=[00 00])
    Toner**     ■■■■■□□□□□ 
         ( from squares c.a. 50.0%  50=[32] 5000=[13 88] | ID=6F: 58.0% 5800=[16 A8] #6F)
```
RAW data organized in segments:
```
#63       1 = 63.0104.00000001         - ? - long shoot: might be drum status (1-ok, 2-ending, 3-used, need replace)
#11    3967 = 11.0104.00000f7f         - Drum count pages
#41    8600 = 41.0104.000021.ffffff.98 – Drum unit remaining life % (in 0.01%)
#31       1 = 31.0104.00000001         - ?
#6F    5800 = 6f.0104.000016.ffffff.a8 – Toner remaining life % (in 0.01%)
#67       1 = 67.0104.00000001         - ?
#6B    7200 = 6b.0104.00001c20         - Fuser unit (or laser unit) remaining life % (in 0.01%)
#54       1 = 54.0104.00000001         - ?
#66       1 = 66.0104.00000001         - ?
#35       3 = 35.0104.00000003         - ?
#6A    7200 = 6a.0104.00001c20         - Laser unit (or fuser unit) remaining life % (in 0.01%)
#6C   10000 = 6c.0104.00002710         - PF Kit MP remaining life % (in 0.01%) 
#6D       0 = 6d.0104.00000000         - PF Kit 1 remaining life % (in 0.01%) (ID from L8650)
#padEnd   = ffffffff
```

### MFC-8880DN - brInfoNextCare

**OID:** `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.11` (**(rInfoNextCare**)

**RAW:**
```
ffffff82010400005229ffffff890104000116077
3010400011607ffffff8601040000ffffffc0ffffffe5
77010400000000ffffffff
```
```
Stream length: 54 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: FF FF FF 82 01 04 00 00 52 29 FF FF FF 89 01 04 ••••••••R)••••••
00000010: 00 01 16 07 73 01 04 00 01 16 07 FF FF FF 86 01 ••••s•••••••••••
00000020: 04 00 00 FF FF FF C0 FF FF FF E5 77 01 04 00 00 •••••••••••w••••
00000030: 00 00 FF FF FF FF                               ••••••
```
HTTP:
```
Remaining Life
    Drum Unit*     21033 pages [52 29] #82   
    Fuser Unit     71175 pages [01 16 07] #89
    Laser Unit     71175 pages [01 16 07] #73
    Paper Feeding Kit MP  49381 pages [C0 E5] #86  
    Paper Feeding Kit 1     0 pages      [00 00] #77
    Toner**     ■■■■■□□□□□ 
```
RAW data organized in segments:
```
#pad       = ffffff
#82  21033 = 82.0104.00005229ffffff           - Drum unit pages
#89  71175 = 89.0104.00011607                 - Fuser unit pages
#73  71175 = 73.0104.00011607ffffff           - Laser unit pages
#86  49381 = 86.0104.0000.ffffff.c0.ffffff.e5 – PF Kit MP pages
#77      0 = 77.0104.00000000                 - PF Kit 1 pages
#padEnd    = ffffffff
```

### MFC-8880DN - brInfoReplaceCount

**OID:** `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.20` (**brInfoReplaceCount**)

**RAW:**
```
ffffff820103ffffffa00117ffffff890102730101ffffff860100770100ffffffff
```
```
Stream length: 34 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: FF FF FF 82 01 03 FF FF FF A0 01 17 FF FF FF 89 ••••••••••••••••
00000010: 01 02 73 01 01 FF FF FF 86 01 00 77 01 00 FF FF ••s••••••••w••••
00000020: FF FF                                           ••
```
HTTP:
```
Replace Count
    Drum Unit              3 [03] #82
    Fuser Unit             1 [01] #73
    Laser Unit             2 [02] #89
    Paper Feeding Kit MP   0 [00] #86
    Paper Feeding Kit 1    0 [00] #77
    Toner                 23 [17] #A0
```
RAW data organized in segments:
```
#pad    = ffffff
#82   3 = 82.01.03ffffff - Drum unit replace count
#A0  23 = a0.01.17ffffff - Toner replace count
#89   2 = 89.01.02       - Laser unit replace count
#73   1 = 73.01.01ffffff - Fuser unit replace count
#86   0 = 86.01.00       - PF Kit MP /or/ Kit 1
#77   0 = 77.01.00       - PF Kit 1 /or/ Kit MP
#padEnd = ffffffff	
```

I have never replaced Laser and Fuser units, but I did from Service Menu
reset them -- lucky me, now I can tell those counters apart :grin: .

### MFC-8880DN - brInfoJamCount

**OID:** `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.21` (**brInfoJamCount**)

**RAW:**
```
00020001010200312102005c22020009
23020005250200ffffffb426020004ffffff
a104000000ffffff9cffffffff
```
```
Stream length: 47 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: 00 02 00 01 01 02 00 31 21 02 00 5C 22 02 00 09 •••••••1!••\"•••
00000010: 23 02 00 05 25 02 00 FF FF FF B4 26 02 00 04 FF #•••%••••••&••••
00000020: FF FF A1 04 00 00 00 FF FF FF 9C FF FF FF FF •••••••••••••••
```
HTTP:
```
Total Paper Jams   156 [00 9C] #A1
    Jam MP Tray      1 [00 01] #00
    Jam Tray 1      49 [00 31] #01
    Jam Inside      92 [00 5C] #21
    Jam Rear         9 [00 09] #22
    Jam Duplex       5 [00 05] #23
Total Paper Jams (ADF SX)***  180 [00 B4] #25
Total Paper Jams (ADF DX)***    4 [00 04] #26
```
RAW data organized in segments:
```
#00     1 = 00.02.0001             - Jam MP Tray
#01    49 = 01.02.0031             - Jam Tray 1
#21    92 = 21.02.005c             - Jam inside
#22     9 = 22.02.0009             - Jam rear
#23     5 = 23.02.0005             - Jam duplex unit
#25   180 = 25.02.00.ffffff.b4     - Total jams at ADF single page
#26     4 = 26.02.0004ffffff      - Total jams at ADF duplex unit
#A1   156 = a1.04.000000.ffffff.9c – Total paper jams
#padEnd   = ffffffff
```