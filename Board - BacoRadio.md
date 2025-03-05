# BacoRadio

## Overal board parts, details, notes

Rectangle, green pcb with 8 white standoffs, a Eurocard female angled socket and 4 empty ram slots.
When I bought it, there was 1 ramslot filled with an odd kind of ram. I may have lost it since.

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

#### XC68SEC811E2FN (Motorola)

#### 515662U96 (Motorola)

#### XC145532L

#### 73K222L-IP / NRN8440A

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