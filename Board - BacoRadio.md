# BacoRadio

## Overal board parts, details, notes

Rectangle, green pcb with 8 white standoffs, a Eurocard female angled socket and 4 empty ram slots.
When I bought it, there was 1 ramslot filled with an odd kind of ram. I may have lost it since.

update 11 march 2025, found a ram stick that fits and looks somewhat like i remmeber. the two stickers on its back match the shape of the other mainboard stickers.

### Roms

2 roms, A and I believe B, the second rom, the apparently larger one is missing its protective film, I also believe i might have removed that at one point and placed protective stickers over teh window later.

The first rom states:
NVN5001A
(C) 1992
MOTOROLA

its an Intel D27C210-200V10
datecode 1988 (U1050183)

The second rom is 

its an Intel D27C220-200V10
datecode 1987 (U1030377)

within the Roms folder I called the one without the label B, as the first one has its label A. Ive made multiple dumps of both and there will be a combined rom that would seem to be the full rom ready for analysis.

Dumps has been made with Minipro TL866CS.

```sh
minipro -p 27C220@DIP40 -r NVN5001B-3.bin
```
adapt where needed.

#### Rom1: NVN5001A
md5: 5d49883c1678ae50e49aea976533d56f

``oCypirhg t9109 ,oMotoral ,nI.cA
llr gith seresvrde``

Due to the m68k being Big endian, we swap each byte. Cause the most significant byte of a word is stored at the smallest memory address.

``Copyright 1990, Motorola, Inc.
All rights reserved.``


#### Rom2: NVN5001B
md5: 78fb960c40e1a57677377955cf3e1e37

``oCypirhg t91091-99,4M torolo,aI cn
.lA lirhgstr sereev.d``

Due to the m68k being Big endian, we swap each byte. Cause the most significant byte of a word is stored at the smallest memory address.

``Copyright 1991-1994, Motorola, Inc.
All rights reserved.``

### Leds

3 leds are onboard,
- CR5, green
- CR6, green
- CR7, red

### Jumpers

2 jumper areas:

- JU1, a 3 pin jumper pins, with 1 jumper accross the 2 pins furthest away from the litium battery (and cpu)
  Might be pins 2 and 3
- JU2 8 pins, 2 jumpers. labeled 1 from lower left, u 2, then right ending with 8 at the upper right
    - 1 jumper on 3-4
    - 1 jumper on 5-6


### IC

#### MC68302CFE16 (Motorola)

According to a datasheet from now MXP, it's a Motorola's mc68302 integrated multi-protocol processor.

``The MC68302 is a versatile one-chip processor that incorporates the main building blocks needed for the
design of a wide variety of networking and communications products. The MC68302 was the first device to
offer the benefits of a closely coupled, industry-standard, MC68000/MC68008 microprocessor core and a
flexible communications architecture. This multi-channel communications device may be configured to
support a number of popular industry-standard interfaces, including those for the Integrated Services Digital
Network (ISDN) basic rate and terminal adapter applications. Through a combination of architectural and
programmable features, concurrent operation of different protocols is easily achieved using the MC68302.
Data concentrators, modems, line cards, bridges, and gateways are examples of other suitable applications for
this versatile device. The MC68302 is an HCMOS device consisting of an MC68000/MC68008
microprocessor core, a system integration block (SIB), and a communications processor (CP)``
https://www.nxp.com/docs/en/fact-sheet/MC68302FACT.pdf


#### MT8981DP 
Digital switch, switching PCM-encoded voice or data, under microprocessor control, in a modern digital exchange, PBX or Central Office.

#### XC68SEC811E2FN (Motorola)

#### 515662U96 (Motorola)

#### XC145532L

#### 73K222L-IP / NRN8440A

#### 2931C (U22)
LDO Voltage Regulator -
Adjustable Output, Load
Dump Protection
60 V, 100 mA

Goes to A31, B31, C31. standby power supply?

#### LM2935T (U40, U15)

a 5 pinned Low dropout dual voltage regulator.
Main is 750mA and can be turned on or of. ythe standby one is up to 10mA for ram for example

"This part was designed for harsh automotive environments and is
therefore immune to many input supply voltage problems such as reverse
battery (–12 V), double battery (+24 V), and load dump transients (+60 V)."

Square pad is pin 1 on the board. on the part, the left side when looking with legs below and label top.
the Motorola side.

1 Input
2 Main output
3 ground
4 Switch/Reset
5 Standby/Output

### DIN41612
Eurocard connector, female, angeled.
96 pins


| Pin Number | A   | Name   | Note    | B   | Name   | Note    | C   | Name   | Note    |
|------------|-----|--------|---------|-----|--------|---------|-----|--------|---------|
| 1          | VCC | input  |         | GND | ground |         | VCC | input  |         |
| 2          |     |        |         | VCC | input  |         | VCC | input  |         |
| 3          | GND | ground |         | GND | ground |         |     |        |         |
| 4          |     |        |         | VCC | input  |         | GND | ground |         |
| 5          | GND | ground |         | GND | ground |         |     |        |         |
| 6          |     |        |         | VCC | input  |         | GND | ground |         |
| 7          | VCC | input  |         | GND | ground |         | VCC | input  |         |
| 8          |     |        |         | VCC | input  |         |     |        |         |
| 9          | VCC | input  |         | GND | ground |         | GND | ground |         |
| 10         | GND | ground |         | VCC | input  |         |     |        |         |
| 11         |     |        |         | GND | ground |         | VCC | input  |         |
| 12         | GND | ground |         | VCC | input  |         |     |        |         |
| 13         | VCC | input  |         | GND | ground |         | VCC | input  |         |
| 14         |     |        |         | VCC | input  |         | GND | ground |         |
| 15         | GND | ground |         | GND | ground |         |     |        |         |
| 16         |     |        |         | VCC | input  |         |     |        |         |
| 17         |     |        |         | GND | ground |         |     |        |         |
| 18         | GND | ground |         | VCC | input  |         | GND | ground |         |
| 19         | VCC | input  |         | GND | ground |         |     |        |         |
| 20         |     |        |         | VCC | input  |         | VCC | input  |         |
| 21         | GND | ground |         | GND | ground |         |     |        |         |
| 22         |     |        |         | VCC | input  |         | GND | ground |         |
| 23         | VCC | input  |         | GND | ground |         | GND | ground |         |
| 24         |     |        |         | VCC | input  |         |     |        |         |
| 25         |     |        |         | GND | ground |         |     |        |         |
| 26         |     |        |         | VCC | input  |         |     |        |         |
| 27         |     |        |         | GND | ground |         |     |        |         |
| 28         | GND | ground |         | VCC | input  |         | GND | ground |         |
| 29         |     |        |         | GND | ground |         |     |        |         |
| 30         | GND | ground |         | GND | ground |         | GND | ground |         |
| 31         |     |        | U22     |     |        | U22     |     |        | U22     |
| 32         | GND | ground |         | GND | ground |         | GND | ground |         |





### PCB markings

### Stickers

#### Gray bottom

#### White small bottom

#### White small top left



#### White small top right

"pass" "B"

## Secondary pcb's

### Clock pcb

Empty back (we see, when installed) and 
silkscreen: QEC-IVO 94V0
2148, 9149

2 ferrite beads, 2 resistors, 2 capasitors.
1 16.304 MHz, OCXO? K11448M
datecode 9149

### Radio pcb 1

### Radio pcb 2

### Ram stick

rectangled green 2 layer pcb. copper layer back sais:
COPYRIGHT MOTOROLA 1990
84D05016W01 REV A

top left sticker:
NVN4004A
9150 MALYSIA

below top left sticker:
PASS

Front side silkscreen:
1566, HI -1, [E] 94V-0
U101 to U104
C101 to C104
Front side IC (times 4):
MCM60L256AFC10
HIQA A9144

#### MCM60L256AFC10

Motorola 32K x 8 Bit CMOS Static Random Access Memory
5V supply, TTL compatible, 100ns memory.

128K total.

