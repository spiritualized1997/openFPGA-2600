# openFPGA-2600
Atari 2600 core for openFPGA on Analogue Pocket
-

Most Atari 2600 things should be supported by this core.

Pretty much every mapper, RAM, and the Supercharger.

Line count and centering are automatically controlled and
should work for just about everything.

The following interact menu items are present:

Region:

You can select NTSC, PAL, SECAM, or automatic.

The latter will automatically select PAL or NTSC depending on the
scanline count. It works most of the time.  The only difference
between any region is just the palette; the timing is set by the
game code.

Swap controllers does what it says, which is useful because some
games treat the left controller as player 1, and others treat right
as player 1.

L Diff A/B selects Advanced or Beginner on the left, and R Diff
does the same for the right player.

TV Type selects color or B&W.

Use Atarivox will enable the Atarivox which can be used with certain
homebrew games.  NOTE: you must have the Atarivox files installed
for this to work.

Next SC Load will trigger the Supercharger "tape player" to press
play on tape.  To run a Supercharger game, you must select this option
on the "Rewind Tape / Press Play" screen. 

For multiload games, you can press this again to select the next
load.

Because Atari 2600 games do not have any kind of header or other method
of determining which mapper is which, the file extention is used to
select one of the mappers if there's ambiguity.  

*.ACT - Activision 8K FE banking
*.PB  - Parker Bros. E0 mapping
*.TV  - Tigervision 3F mapping  
*.TVR - Tigervision 3E (with RAM) mapping
*.MN  - M-network E7 mapping
*.CV  - Commavid extra RAM
*.EB  - Econobanking
*.EF  - EF Bankswitching
*.EFR - EF with RAM
*.UA  - UA bankswitching
*.X07 - X07 bankswitching
*.SB  - Superbanking

The following do not need an extension.

(filesize)
2048 bytes - standard 2K game, no bankswitching
4096 bytes - standard 4K game, no bankswitching
8192 bytes - standard 8K game, uses F8 (FFF8/FFF9) bankswitching
16384 bytes - standard 16K game, uses F6 (FFF6-FFF9) bankswitching
32768 bytes - standard 32K game, uses F4 (FFF4-FFFA) bankswitching
65536 bytes - Dynacom Megaboy
12288 bytes - RAM+ (FA)
10240 bytes - Pitfall 2 (DPC)
10495 bytes - Pitfall 2 (DPC)
24576 bytes - 24K (FA2)
8448 bytes - Supercharger single load
16896 bytes - Supercharger dual load
25344 bytes - Supercharger triple load
33792 bytes - Supercharger quad load
67584 bytes - Supercharger demo unit

"Superchip" RAM is detected by reading the first 256 bytes of the
file and checking for all 00's or FF's.  If either condition 
exists, extra RAM is assumed for 8K, 16K, and 32K standard games.


Required files:

Supercharger bios file.  It is 2048 bytes.  It has the filename "scbios.bin".

/assets/2600/Spiritualized.2600/scbios.bin

Supercharger loader. It is 2048 bytes.  It is included with this release.

/assets/2600/Spiritualized.2600/sc_load.bin

Atarivox PRG ROM. It is 8192 bytes. It has the filename "avoxrom.bin".

/assets/2600/Spiritualized.2600/avoxrom.bin

Atarivox EEPROM.  It is 256 bytes. It has the filename "avoxee.bin".

/assets/2600/Spiritualized.2600/avoxee.bin
