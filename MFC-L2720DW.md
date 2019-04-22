## MFC-L2720DW

On this printer no one bothered ever to reset drum counter :smile: so the
drum have insane endurance :laughing: . Printer with new web UI.

### MFC-L2720DW - brInfoCounter

**OID:** `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.10` (**brInfoCounter**)

**RAW:** `0001040001ffffff8dffffff9fffffffff`
```
Stream length: 17 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: 00 01 04 00 01 FF FF FF 8D FF FF FF 9F FF FF FF ••••••••••••••••
00000010: FF                                              •
```
HTTP:
```
Node Information
	Model Name: Brother MFC-L2720DW series
	Main Firmware Version: L
	Sub1 Firmware Version: 1.06
	Sub2 Firmware Version: F1512090500
	Memory Size: 64MB
Device Status
	Page Counter         : 101791 [01 8D 9F] #00
```
RAW data organized in segments:
```
#00   101791 = 00.0104.0001.ffffff.8d.ffffff.9f - page counter
#padEnd      = ffffffff
```

### MFC-L2720DW - brInfoCoverage

**OID:** `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.18` (**brInfoCoverage**)

**RAW:** `00020529ffffffff`
```
Stream length: 8 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: 00 02 05 29 FF FF FF FF                         •••)••••
```
HTTP:
```
Device Status
	Page Counter         : 101791 [01 8D 9F]
	Drum Count           : 101791 [01 8D 9F]
	Average Coverage**** : 5.41%  [05 29] ( 5=0x05 integer , 41=0x29 decimal) #00
```
RAW data organized in segments:
```
#00   5 41 = 00.02.0529 - Coverage
#padEnd    = ffffffff
```

### MFC-L2720DW - brInfoMaintenance

**OID**: `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.8` (**brInfoMaintenance**)

**RAW:**
```
630104000000031101040001ffffff8dffffff9f
41010400000000310104000000016f0104000009ffffffc4ffffff
8101040000001effffff8601040000000affffffff
```
```
Stream length: 68 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: 63 01 04 00 00 00 03 11 01 04 00 01 FF FF FF 8D c•••••••••••••••
00000010: FF FF FF 9F 41 01 04 00 00 00 00 31 01 04 00 00 ••••A••••••1••••
00000020: 00 01 6F 01 04 00 00 09 FF FF FF C4 FF FF FF 81 ••o•••••••••••••
00000030: 01 04 00 00 00 1E FF FF FF 86 01 04 00 00 00 0A ••••••••••••••••
00000040: FF FF FF FF                                     ••••
```
HTTP:
```
Remaining Life
	Drum Unit*            : 0pages  [00 00]
	(% of Life Remaining) : (0.00%) [00 00] #41
```
This printer returns via http not much data :neutral_face: .

RAW data organized in segments:
```
#63       3 = 63.0104.00000003                 - ? long shoot: might be drum status (1-ok, 2-ending, 3-used, need replace)
#11  101791 = 11.0104.0001.ffffff.8d.ffffff.9f – Drum page count (^o^)
#41       0 = 41.0104.00000000                 - Remaining life: drum (in 0.01%)
#31       1 = 31.0104.00000001                 - ?
#6F    2500 = 6f.0104.000009.ffffff.c4.ffffff  - ? - Remaining life: toner (in 0.01%)
#81      30 = 81.0104.0000001e.ffffff          - ? - Remaining life: toner (in 1% (step 10%?))
#86      10 = 86.0104.0000000a                 - ? – Remaining life: toner - min warn level?
#padEnd     = ffffffff
```

### MFC-L2720DW - brInfoNextCare

**OID:** `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.11` (**brInfoNextCare**)

**RAW:** `ffffff82010400000000ffffffff`
```
Stream length: 14 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: FF FF FF 82 01 04 00 00 00 00 FF FF FF FF       ••••••••••••••
```
HTTP:
```
Remaining Life
	Drum Unit*   : 0pages  [00 00] #82
```
RAW data organized in segments:
```
#pad     = ffffff
#82    0 = 82.0104.00000000 – Remaining life: drum unit (in pages)
#padEnd  = ffffffff
```

### MFC-L2720DW - brInfoReplaceCount

**OID:** `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.20` (**brInfoReplaceCount**)

**RAW:** `ffffff820100ffffffa0012fffffffff`
```
Stream length: 16 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: FF FF FF 82 01 00 FF FF FF A0 01 2F FF FF FF FF •••••••••••/••••
```
HTTP:
```
Replace Count
	Toner     : 47 [2F] #A0
	Drum Unit : 0  [00] #82
```
RAW data organized in segments:
```
#pad    = ffffff
#82   0 = 82.01.00.ffffff – drum replace count
#A0  47 = a0.01.2f        - toner replace count
#padEnd = ffffffff
```

### MFC-L2720DW - brInfoJamCount

**OID:** `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.21` (**brInfoJamCount**)

**RAW:**
```
010200022102001322020011230200002502001bffffff
a10400000026ffffffff
```
```
Stream length: 33 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: 01 02 00 02 21 02 00 13 22 02 00 11 23 02 00 00 ••••!•••"•••#•••
00000010: 25 02 00 1B FF FF FF A1 04 00 00 00 26 FF FF FF %•••••••••••&•••
00000020: FF                                              •
```
HTTP:
```
Total Paper Jams : 38 [00 26] #A1
	Jam Tray 1   : 2  [00 02] #01
	Jam Inside   : 19 [00 13] #21
	Jam Rear     : 17 [00 11] #22
	Jam 2-sided  : 0  [00 00] #23
Total Paper Jams (ADF)*** : 27 [00 1B] #27
```
RAW data organized in segments:
```
#01   2 = 01.02.0002        - Jam count: Tray 1
#21  19 = 21.02.0013        - Jam count: inside
#22  17 = 22.02.0011        - Jam count: rear
#23   0 = 23.02.0000        - Jam count: duplex unit
#25  27 = 25.02.001b.ffffff - Jam count: ADF
#A1  38 = a1.04.00000026    - Total paper jam count
#padEnd = ffffffff
```