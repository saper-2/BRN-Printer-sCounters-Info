## MFC- B7715DW

This is a rather new printer (compared to 8880DN :D ), it have also new
web UI.

### MFC-B7715DW - brInfoCounter

**OID:** `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.10` (**brInfoCounter**)

**RAW:** `00010400002a3e06010400000236ffffffff`
```
Stream length: 18 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: 00 01 04 00 00 2A 3E 06 01 04 00 00 02 36 FF FF •••••*>••••••6••
00000010: FF FF                                           ••
```
HTTP:
```
Node Information
	Model Name            : Brother MFC-B7715DW series
	Main Firmware Version : H
	Sub1 Firmware Version : 1.04
	Memory Size           : 128MB
Device Status
	Page Counter          : 10814 [2A 3E] #00
Total Pages Printed
	Total         : 10814Page(s) [2A 3E] #00
	2-sided Print : 566          [02 36] #06
```
RAW data organized in segments:
```
#00  10814 = 00.0104.00002a3e – Page counter
#06    566 = 06.0104.00000236 – Duplex unit pages 
#padEnd    = ffffffff
```

### MFC- B7715DW - brInfoCoverage

**OID:** `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.18` (**brInfoCoverage**)

**RAW:** `0002050dffffffff`
```
Stream length: 8 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: 00 02 05 0D FF FF FF FF                         ••••••••
```
HTTP:
```
Node Information
	Model Name            : Brother MFC-B7715DW series
Device Status
	Page Counter          : 10814 [2A 3E]
	Average Coverage****  : 5.13% [05 0D] #00 (5=0x05 integer , 13=0x0D decimal)
```
RAW data organized in segments:
```
#00  5 13 = 00.02.050d - Average Coverage
#padEnd   = ffffffff
```

### MFC- B7715DW - brInfoMaintenance

**OID**: `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.8` (**brInfoMaintenance**)

**RAW:**
```
63010400000001410104000003ffffffe811010400002a39
310104000000016f010400001dffffffb0ffffff
81010400000050ffffffff
```
```
Stream length: 55 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: 63 01 04 00 00 00 01 41 01 04 00 00 03 FF FF FF c••••••A••••••••
00000010: E8 11 01 04 00 00 2A 39 31 01 04 00 00 00 01 6F ••••••*91••••••o
00000020: 01 04 00 00 1D FF FF FF B0 FF FF FF 81 01 04 00 ••••••••••••••••
00000030: 00 00 50 FF FF FF FF                            ••P••••
```
HTTP:
```
Device Status
	Page Counter: 10814 [2A 3E]
Remaining Life
	Drum Unit*  : 10% [03 E8] (in 0.01% => 1000=10%) #41
	Toner**     : 80% [00 50] #81
```
If we add `#11`=10809 to **brInfoNextCare** `#82`=1191 then we get 12000
which is a drum unit page life.

RAW data organized in segments:
```
#63     1 = 63.0104.00000001                - ? - long shoot: might be drum status (1-ok, 2-ending, 3-used, need replace)
#41  1000 = 41.0104.000003.ffffff.e8        - Remaining life: drum unit (in 0.01%)
#11 10809 = 11.0104.00002a39                - Drum unit page count (?)
#31     1 = 31.0104.00000001                - ?
#6f  7600 = 6f.0104.00001d.ffffff.b0.ffffff - ?
#81    80 = 81.0104.00000050                - Remaining life: Toner (in 1%)
#padEnd   = ffffffff
```

### MFC- B7715DW - brInfoNextCare

**OID:** `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.11` (**brInfoNextCare**)

**RAW:** `ffffff820104000004ffffffa7ffffffff`
```
Stream length: 17 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: FF FF FF 82 01 04 00 00 04 FF FF FF A7 FF FF FF ••••••••••••••••
00000010: FF                                              •
```
HTTP:
```
Remaining Life
	Drum Unit*  : 10% [0A] / [03 E8] 
```

10% from 12000p = 1200, the value 1191 fit the bill (1191\*100/12000=9,925% = \~10% )

RAW data organized in segments:
```
#pad      = ffffff
#82  1191 = 82.0104.000004.ffffff.a7 – drum unit remaining life (pages)
#padEnd   = ffffffff
```

### MFC- B7715DW - brInfoReplaceCount

**OID:** `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.20` (**brInfoReplaceCount**)

**RAW:** `ffffff820101ffffffa00106ffffffff`
```
Stream length: 16 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: FF FF FF 82 01 01 FF FF FF A0 01 06 FF FF FF FF ••••••••••••••••
```
HTTP:
```
Replace Count
	Toner     : 6 [06] #A0
	Drum Unit : 1 [01] #82
```
RAW data organized in segments:
```
#pad   = ffffff
#82   1 = 82.01.01 ffffff – Drum replace count
#A0   6 = a0.01.06        - Toner replace count
#padEnd = ffffffff
```

### MFC- B7715DW - brInfoJamCount

**OID:** `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.21` (**brInfoJamCount**)

**RAW:**
```
000200000102000021020000220200002302000025020001ffffff
a10400000000ffffffff
```
```
Stream length: 37 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: 00 02 00 00 01 02 00 00 21 02 00 00 22 02 00 00 ••••••••!•••"•••
00000010: 23 02 00 00 25 02 00 01 FF FF FF A1 04 00 00 00 #•••%•••••••••••
00000020: 00 FF FF FF FF                                  •••••
```
HTTP:
```
Total Paper Jams: 0 [00 00] #A1
	Jam Tray 1  : 0 [00 00] #01
	Jam Inside  : 0 [00 00] #21
	Jam Rear    : 0 [00 00] #22
	Jam 2-sided : 0 [00 00] #23
Total Paper Jams (ADF)*** : 1 [00 01] #25
```
*Because this printer don't have any jams (yet), I identified IDs using
previous findings.*

RAW data organized in segments:
```
#00   0 = 00.02.0000        - Jam count: MP Tray 
#01   0 = 01.02.0000        - Jam count: Tray 1
#21   0 = 21.02.0000        - Jam count: inside
#22   0 = 22.02.0000        - Jam count: rear
#23   0 = 23.02.0000        - Jam count: duplex unit
#25   1 = 25.02.0001.ffffff - Jam count: ADF
#A1   0 = a1.04.00000000    - Total paper jam count 
#padEnd = ffffffff
```