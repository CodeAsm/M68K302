# MC68302 (Military) Radio PCB Analysis

This repository contains all my notes, code dumps, and analysis of an old military PCB, likely a radio transceiver board.

## Contents

- **Notes**: Detailed observations and insights about the PCB components and their functions.
- **Code Dumps**: Scripts and code snippets used during the analysis.
- **Analysis**: In-depth examination and findings related to the PCB.

## Purpose

The goal of this project is to reverse engineer and understand the workings of the military radio transceiver board.
Probably not in full, but well enough to tease my brain.

## Disclaimer

This project is for educational purposes only. Any sensitive information has been redacted.

## Further resources

A few projects seem to excist. these may help a bit with touching the cpu.

- Tiny302, a minimalist singleboard computer based on the MC68302, the thread it links to seems dead.
  https://github.com/Plasmode/Tiny302
- Kicad designs for a "MC68302-based CPU card and backplane system " 
  https://github.com/kvanderlaag/malebolge
- Musashi is an Motorola 680x0 emulator, might be intresting, but probably not compatible as-is
  https://github.com/kstenerud/Musashi.git

- official old resources:
    - https://web.archive.org/web/19990429172627/http://www.mot.com/SPS/RISC/netcomm/prod/3XX/68302.html
    - https://web.archive.org/web/19990503174834/http://www.mot.com/SPS/RISC/netcomm/docs/pr/302.html
    - https://web.archive.org/web/19990429113602/http://www.mot.com/SPS/RISC/netcomm/tools/thirdpty/302.html#swchip

- Old devboard for sale https://www.artisantg.com/Embedded/62472-2/Emerson-Motorola-M68302ADS-Application-Development-System-VME-Board
- Another one for sale, with manual and closeup https://www.ricardo.ch/de/a/vintage-motorola-m68302-sdk-(komunikation)-1213043282/


- Microtec compiler manual https://archive.org/details/microtec-68-k-asm-link-lib/Microtec_68K_Asm_Link_Lib/page/n7/mode/2up
- Compiler in awefull state https://archive.org/details/mri-mcc-68-k-v-4-3-k
- A Compiler set on original diskette images https://archive.org/details/mri-68-k-c-cross-compiler-toolchain
- I dont know https://github.com/ysh86/CC68K