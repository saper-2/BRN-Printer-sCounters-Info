## DCP-7065DN

This printer using older web UI and it have a bit different segment
layout for **brInfoCounter**: value is split into 2x16bit pieces with
3xFF separator.

### DCP-7065DN - brInfoCounter

**OID:** `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.10` (**brInfoCounter**)

**RAW:** `0001040000fffffffb2bffffffff`

```
Stream length: 14 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: 00 01 04 00 00 FF FF FF FB 2B FF FF FF FF       •••••••••+••••
```
HTTP:
```
Node Information
    Model Name       : Brother DCP-7065DN
    Firmware Version : J
    Memory Size      : 32 Mbytes
Device Status
    Page Counter : 64299 [FB 2B] #00
    Drum Count   : 25642 [64 2A]

```
RAW data organized in segments:
```
#00  64299 = 00.0104.0000.fffffffb2bffffffff – page counter 
#padEnd    = ffffffff 
```

 ### DCP-7065DN - brInfoMaintenance

**OID**: `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.8` (**brInfoMaintenance**)

**RAW:**
```
630104000000031101040000642a
4101040000000031010400000001
6f010400000fffffffa0ffffffff
```
```
Stream length: 42 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: 63 01 04 00 00 00 03 11 01 04 00 00 64 2A 41 01 c•••••••••••d*A•
00000010: 04 00 00 00 00 31 01 04 00 00 00 01 6F 01 04 00 •••••1••••••o•••
00000020: 00 0F FF FF FF A0 FF FF FF FF                   ••••••••••
```
HTTP:
```
Node Information
    Model Name       : Brother DCP-7065DN
Device Status
    Page Counter     : 64299 [FB 2B] 
    Drum Count       : 25642 [64 2A] #11
Remaining Life
    Drum Unit*       : 0 pages [00 00] (% of Life Remaining: 0.00% [00 00] #41)
    Toner**          : ■■■■□□□□□□ (c.a. 40% left 4000=[0F A0] #6F ) 
Total Pages Printed
    Plain/Thin/Recycled            : 64303 pages [FB 2F]
    Thick/Thicker/Bond             : 1 pages [00 01]
    Envelopes/Env. Thick/Env. Thin : 0 pages [00 00]
    Label                          : 0 pages [00 00]
Replace Count
    Drum Unit :  3 [00 03] #63
    Toner     : 24 [00 18]
```
RAW reorganized into segments:
```
#63      3 = 63.0104.00000003         - ? - long shoot: might be drum status (1-ok, 2-ending, 3-used, need replace)
#11  25642 = 11.0104.0000642a         - Drum page count
#41      0 = 41.0104.00000000         - Drum unit remaining life [in 0.01%]
#31      1 = 31.0104.00000001         - ? ? ? 
#6f   4000 = 6f.0104.00000f.ffffff.a0 – Toner remaining life [in 0.01%]
#pad       = ffffffff
```

### DCP-7065DN - brInfoNextCare

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
    Drum Unit*       : 0 pages [00 00] #82 
    Toner**     ■■■■□□□□□□ (c.a. 40% left 4000=[0F A0] / 40=[28])
```
RAW reorganized into segments:
```
#pad      = ffffff
#82     0 = 82.0104.00000000  - Drum remaining life pages
#padEnd   = ffffffff
```

### DCP-7065DN - brInfoReplaceCount

**OID:** `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.20` (**brInfoReplaceCount**)

**RAW:** `ffffff820103ffffffa00118ffffffff`
```
Stream length: 16 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: FF FF FF 82 01 03 FF FF FF A0 01 18 FF FF FF FF ••••••••••••••••
```
HTTP:
```
Replace Count
    Drum Unit :  3 [03] #82
    Toner     : 24 [18] #A0
```
RAW reorganized into segments:
```
#pad      = ffffff     
#82     3 = 82.01.03ffffff - Drum replace count
#A0    24 = a0.01.18       - Toner replace count
#padEnd   = ffffffff
```

### DCP-7065DN - brInfoJamCount

**OID:** `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.21` (**brInfoJamCount**)

**RAW:**
```
010200022102000a220200012302000025020014ffffffa1040000000dffffffff
```
```
Stream length: 33 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: 01 02 00 02 21 02 00 0A 22 02 00 01 23 02 00 00 ••••!•••"•••#•••
00000010: 25 02 00 14 FF FF FF A1 04 00 00 00 0D FF FF FF %•••••••••••••••
00000020: FF                                              •
```
HTTP:
```
Total Paper Jams : 13 [00 00 00 0D] #A1
    Jam Tray 1   : 2  [00 02] #01
    Jam Inside   : 10 [00 0A] #21
    Jam Rear     : 1  [00 01] #22
    Jam Duplex   : 0  [00 00] #23
Total Paper Jams (ADF)*** : 20 [00 14] #25
```
RAW reorganized into segments:
```
#01    2 = 01.02.0002       - Paper jam count: tray 1
#21   10 = 21.02.000a       - Paper jam count: inside
#22    1 = 22.02.0001       - Paper jam count: rear
#23    0 = 23.02.0000       - Paper jam count: duplex unit
#25   20 = 25.02.0014ffffff - Paper jam count: ADF
#a1   13 = a1.04.0000000d   - Total paper jam count
#padEnd  = ffffffff
```