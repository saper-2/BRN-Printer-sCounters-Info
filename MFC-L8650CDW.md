## MFC-L8650CDW

This printer have new web UI, but don't have yet implemented calculation
of page coverage.

### MFC-L8650CDW - brInfoCounter

**OID:** `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.10` (**brInfoCounter**)

**RAW:**
```
000104000021fffffffa020104000013ffffffd001010400000e2a
160104000056ffffffa113010400001350140104000013ffffffd0
15010400000dffffffcd120104000021ffffffb4ffffffff
```
```
Stream length: 78 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: 00 01 04 00 00 21 FF FF FF FA 02 01 04 00 00 13 •••••!••••••••••
00000010: FF FF FF D0 01 01 04 00 00 0E 2A 16 01 04 00 00 ••••••••••*•••••
00000020: 56 FF FF FF A1 13 01 04 00 00 13 50 14 01 04 00 V••••••••••P••••
00000030: 00 13 FF FF FF D0 15 01 04 00 00 0D FF FF FF CD ••••••••••••••••
00000040: 12 01 04 00 00 21 FF FF FF B4 FF FF FF FF       •••••!••••••••

```
HTTP:
```
Device Status
	Page Counter     :  8698 [21 FA] #00 (this might be in brInfoMaintenance?)
	Color            :  5072 [13 D0] #02
	B&W              :  3626 [0E 2A] #01
	Image Count Total: 22177 [56 A1] #16
	Cyan             :  4944 [13 50] #13
	Magenta          :  5072 [13 D0] #14
	Yellow           :  3533 [0D CD] #15
	Black            :  8628 [21 B4] #12
	Drum Count       :  8698 [21 FA] #00

```
RAW data organized in segments:
```
#00   8698 = 00.0104.000021.ffffff.fa – drum count
#02   5072 = 02.0104.000013.ffffff.d0 – Color page count
#01   3626 = 01.0104.00000e2a         – B/W page count
#16  22177 = 16.0104.000056.ffffff.a1 – Image count total
#13   4944 = 13.0104.00001350         – Cyan color count
#14   5072 = 14.0104.000013.ffffff.d0 – Magenta color count
#15   3533 = 15.0104.00000d.ffffff.cd – Yellow color count
#12   8628 = 12.0104.000021.ffffff.b4 – Black color count
#padEnd    = ffffffff

```

 ### MFC-L8650CDW - brInfoMaintenance

**OID**: `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.8` (**brInfoMaintenance**)

**RAW:**
```
630104000000016801040000000155010400000001310104000000013
20104000000013301040000000134010400000001700104000011ffffff94ffffff
8201040000003271010400001518ffffff8301040000003c7
2010400001518ffffff8401040000003c6f010400001effffffdcffffff
81010400000050ffffff8701040000000affffff8801040000000affffff
8901040000000affffff8601040000000a410104000019ffffffc8
69010400001bffffffbc110104000021fffffff967010400000001
6b0104000023fffffff05401040000000166010400000001
350104000000016a0104000023fffffff06c0104000027106d010400002454ffffffff
```

```
Stream length: 259 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: 63 01 04 00 00 00 01 68 01 04 00 00 00 01 55 01 c••••••h••••••U•
00000010: 04 00 00 00 01 31 01 04 00 00 00 01 32 01 04 00 •••••1••••••2•••
00000020: 00 00 01 33 01 04 00 00 00 01 34 01 04 00 00 00 •••3••••••4•••••
00000030: 01 70 01 04 00 00 11 FF FF FF 94 FF FF FF 82 01 •p••••••••••••••
00000040: 04 00 00 00 32 71 01 04 00 00 15 18 FF FF FF 83 ••••2q••••••••••
00000050: 01 04 00 00 00 3C 72 01 04 00 00 15 18 FF FF FF •••••<r•••••••••
00000060: 84 01 04 00 00 00 3C 6F 01 04 00 00 1E FF FF FF ••••••<o••••••••
00000070: DC FF FF FF 81 01 04 00 00 00 50 FF FF FF 87 01 ••••••••••P•••••
00000080: 04 00 00 00 0A FF FF FF 88 01 04 00 00 00 0A FF ••••••••••••••••
00000090: FF FF 89 01 04 00 00 00 0A FF FF FF 86 01 04 00 ••••••••••••••••
000000A0: 00 00 0A 41 01 04 00 00 19 FF FF FF C8 69 01 04 •••A•••••••••i••
000000B0: 00 00 1B FF FF FF BC 11 01 04 00 00 21 FF FF FF ••••••••••••!•••
000000C0: F9 67 01 04 00 00 00 01 6B 01 04 00 00 23 FF FF •g••••••k••••#••
000000D0: FF F0 54 01 04 00 00 00 01 66 01 04 00 00 00 01 ••T••••••f••••••
000000E0: 35 01 04 00 00 00 01 6A 01 04 00 00 23 FF FF FF 5••••••j••••#•••
000000F0: F0 6C 01 04 00 00 27 10 6D 01 04 00 00 24 54 FF •l••••'•m••••$T•
00000100: FF FF FF                                        •••
```
HTTP:
```
Node Information
	Model Name: Brother MFC-L8650CDW
Device Status
	Page Counter     :  8697 [21 F9] #11 (this might actually in brInfoCounter ??)
	Drum Count       :  8697 [21 F9] #11
Remaining Life
	Drum Unit*: 16303pages [3F AF] ; max=25000 (% of Life Remaining): (66.00%) (6600= 19 C8) #41
	Belt Unit:  35302pages [89 E6] ; 50000-35302=14698[39 6A] (% of Life Remaining): (71.00%) (7100= 1B BC) #69
	Fuser Unit: 91303pages [01 64 A7]; max=100000 (% of Life Remaining): (92.00%)  (9200 = 23 F0) #6B (or #6A)
	Laser Unit: 91303pages [01 64 A7]; max=100000 (% of Life Remaining): (92.00%)  (9200= 23 F0) #6A (or #6B)
	Paper Feeding Kit MP: 49542pages [C1 86] ; max=60000? (% of Life Remaining): (100.00%)  (10000= 27 10)
	Paper Feeding Kit 1: 92666pages [01 69 FA] ; max=100000 (% of Life Remaining): (93.00%) (9300= 24 54)
	Toner Cyan (C)**: (50.00%) [32] #82    / #87 = 10 [0A] – minimum warning level? (Cyan)
	Toner Magenta (M)**: (60.00%) [3C] #83 / #88 = 10 [0A] - minimum warning level? (magenta)
	Toner Yellow (Y)**: (60.00%) [3C] #84  / #89 = 10 [0A] - minimum warning level? (yellow)
	Toner Black (BK)**: (80.00%) [50] #81  / #86 = 10 [0A] - minimum warning level? (black)
          Looking how toner colors are in sequence (3 indexes in succession, 
          followed by 4th that is lower than first) -  I think is safely to assume that that kind of data constructions refer to toners.

```
RAW reorganized into segments:
```
#63      1 = 63.0104.00000001              – ? - long shoot: might be drum status (1-ok, 2-ending, 3-used, need replace)
#68      1 = 68.0104.00000001              – ?
#55      1 = 55.0104.00000001              – ?
#31      1 = 31.0104.00000001              – ?
#32      1 = 32.0104.00000001              – ?
#33      1 = 33.0104.00000001              – ?
#34      1 = 34.0104.00000001              – ?
#70   4500 = 70.0104.000011ffffff94ffffff  – ?
#82     50 = 82.0104.00000032              – Toner cyan level in 1%
#71   5400 = 71.0104.00001518ffffff        – ?
#83     60 = 83.0104.0000003c              – Toner magenta level in 1%
#72   5400 = 72.0104.00001518ffffff        – ?
#84     60 = 84.0104.0000003c              – Toner yellow level in 1%
#6f   7900 = 6f.0104.00001effffffdcffffff  – ?
#81     80 = 81.0104.00000050ffffff        – Toner black level in 1%
#87     10 = 87.0104.0000000affffff        – ?
#88     10 = 88.0104.0000000affffff        – ?
#89     10 = 89.0104.0000000affffff        – ?
#86     10 = 86.0104.0000000a              – ?
#41   6600 = 41.0104.000019ffffffc8        – Drum unit remaining life in 0.01%
#69   7100 = 69.0104.00001bffffffbc        – Belt unit remaining life in 0.01%
#11   8697 = 11.0104.000021fffffff9        – Drum unit page count
#67      1 = 67.0104.00000001              – ?
#6b   9200 = 6b.0104.000023fffffff0        – Fuser/Laser unit remaining life in 0.01%
#54      1 = 54.0104.00000001              – ?
#66      1 = 66.0104.00000001              – ?
#35      1 = 35.0104.00000001              – ?
#6a   9200 = 6a.0104.000023fffffff0        – Fuser/Laser unit remaining life in 0.01%
#6c  10000 = 6c.0104.00002710              – PF KIT MP remaining life in 0.01%
#6d   9300 = 6d.0104.00002454              – PF KIT 1 remaining life in 0.01%
#padEnd    = ffffffff
```

It's difficult to tell if `#6B`/`#6A` is a laser or fuser remaining life
because those are almost never replaced and theirs counters are always
identical.

### MFC-L8650CDW - brInfoNextCare

**OID:** `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.11` (**brInfoNextCare**)

**RAW:**
```
ffffff82010400003fffffffafffffff8801040000ffffff89ffffffe6ffffff
890104000164ffffffa7730104000164ffffffa7ffffff8601040000ffffffc1ffffff
86770104000169fffffffaffffffff
```

```
Stream length: 82 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: FF FF FF 82 01 04 00 00 3F FF FF FF AF FF FF FF ••••••••?•••••••
00000010: 88 01 04 00 00 FF FF FF 89 FF FF FF E6 FF FF FF ••••••••••••••••
00000020: 89 01 04 00 01 64 FF FF FF A7 73 01 04 00 01 64 •••••d••••s••••d
00000030: FF FF FF A7 FF FF FF 86 01 04 00 00 FF FF FF C1 ••••••••••••••••
00000040: FF FF FF 86 77 01 04 00 01 69 FF FF FF FA FF FF ••••w••••i••••••
00000050: FF FF                                           ••
```
HTTP:
```
Node Information
	Model Name: Brother MFC-L8650CDW
Remaining Life
	Drum Unit*: 16303pages [3F AF] #82 ; max=25000
	Belt Unit: 35302pages [89 E6] #88 ; 50000-35302=14698[39 6A]
	Fuser Unit: 91303pages [01 64 A7] #89 ; max=100000
	Laser Unit: 91303pages [01 64 A7] #73 ; max=100000
	Paper Feeding Kit MP: 49542pages [C1 86] #86 ; max=50000
	Paper Feeding Kit 1: 92666pages [01 69 FA] #? ; max=100000
```
I think the value in `#77` relate to wear level of mechanics after fuser
that redirect a sheet for duplex printing - I'm guessing only , it
might be also PFK counter which exclude front trays...

RAW reorganized into segments:
```
#pad       = ffffff      
#82  16303 = 82.0104.00003fffffffafffffff       - Drum unit remaining pages count
#88  35302 = 88.0104.0000ffffff89ffffffe6ffffff – Belt unit remaining pages count
#89  91303 = 89.0104.000164ffffffa7             - Fuser unit remaining pages count
#73  91303 = 73.0104.000164ffffffa7ffffff       - Laser unit remaining pages count
#86  49542 = 86.0104.0000ffffffc1ffffff86       - PF Kit MP remaining pages count
#77  92591 = 77.0104.000169fffffffa             - PF Kit 1? remaining pages count (value: 92666)
#padEnd    = ffffffff
```

### MFC-L8650CDW - brInfoReplaceCount

**OID:** `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.20` (**brInfoReplaceCount**)

**RAW:**
```
ffffff870100ffffffa10103ffffffa20102ffffffa30102ffffff
820100ffffffa00104ffffff880100ffffff890100730100ffffff
860100770100ffffffff
```

```
Stream length: 64 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: FF FF FF 87 01 00 FF FF FF A1 01 03 FF FF FF A2 ••••••••••••••••
00000010: 01 02 FF FF FF A3 01 02 FF FF FF 82 01 00 FF FF ••••••••••••••••
00000020: FF A0 01 04 FF FF FF 88 01 00 FF FF FF 89 01 00 ••••••••••••••••
00000030: 73 01 00 FF FF FF 86 01 00 77 01 00 FF FF FF FF s••••••••w••••••
```
HTTP:
```
Replace Count
	Toner Cyan (C)      : 3 [03]
	Toner Magenta (M)   : 2 [02]
	Toner Yellow (Y)    : 2 [02]
	Toner Black (BK)    : 4 [04]
	Drum Unit           : 0 [00]
	Belt Unit           : 0 [00]
	Fuser Unit          : 0 [00]
	Laser Unit          : 0 [00]
	Paper Feeding Kit MP: 0 [00]
	Paper Feeding Kit 1 : 0 [00]
	Waste Toner Box     : 0 [00]
```
All values where is 0 - I'm only guessing what it refer to, by looking
at segment Id from previous sections.

RAW reorganized into segments:
```
#pad    = ffffff
#87   0 = 87.01.00ffffff   - Toner waste box (? not sure) replace counter
#a1   3 = a1.01.03ffffff   - Toner cyan replace counter
#a2   2 = a2.01.02ffffff   - Toner magenta replace counter
#a3   2 = a3.01.02ffffff   - Toner yellow replace counter
#82   0 = 82.01.00ffffff   - Drum unit (?) replace counter
#a0   4 = a0.01.04ffffff   - Toner black replace counter
#88   0 = 88.01.00ffffff   - Belt unit (?) replace counter
#89   0 = 89.01.00         - Fuser unit (?) replace counter
#73   0 = 73.01.00ffffff   - Laser unit (?) replace counter
#86   0 = 86.01.00         - PF Kit MP (?) replace counter
#77   0 = 77.01.00         – PF Kit 1 (?) replace counter
#padEnd = ffffffff
```

### MFC-L8650CDW - brInfoJamCount

**OID:** `1.3.6.1.4.1.2435.2.3.9.4.2.1.5.5.21` (**brInfoJamCount**)

**RAW:**
```
00020003010200012102000222020000
230200002502000126020000ffffff
a10400000006ffffffff
```
```
Stream length: 41 bytes
Table width: 16 bytes
ADDRESS : 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F 0123456789ABCDEF
--------  -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- ----------------
00000000: 00 02 00 03 01 02 00 01 21 02 00 02 22 02 00 00 ••••••••!•••"•••
00000010: 23 02 00 00 25 02 00 01 26 02 00 00 FF FF FF A1 #•••%•••&•••••••
00000020: 04 00 00 00 06 FF FF FF FF                      •••••••••

```
HTTP:
```
Total Paper Jams : 6 [06] #A1
    Jam MP Tray  : 3 [03] #00
    Jam Tray 1   : 1 [01] #01
    Jam Inside   : 2 [02] #21
    Jam Rear     : 0 [00] #22
    Jam 2-sided  : 0 [00] #23
    Total Paper Jams (ADF 1-sided): 1 [01] #25
    Total Paper Jams (ADF 2-sided): 0 [00] #26
```
RAW reorganized into segments:
```
#00  3 = 00.02.0003              - Jam count at MP tray
#01  1 = 01.02.0001              - Jam count at Tray 1
#21  2 = 21.02.0002              - Jam count inside
#22  0 = 22.02.0000              - Jam count in rear
#23  0 = 23.02.0000              - Jam count at duplex unit
#25  1 = 25.02.0001              - Jam count at ADF single side
#26  0 = 26.02.0000ffffff        - Jam count at ADF duplex unit
#A1  6 = a1.04.00000006          – Total jam count
#pad   = ffffffff
```