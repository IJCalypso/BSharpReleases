# BSharp
BBC Micro emulator written in C# using:  
Avalonia UI for the user interface  
Silk.Net (OpenAL for sound and GLFW for handling a USB joystick)

Codebase will compile for:

Windows  
<img src="./Images/v1_1_0_Windows.png" alt="Windows" width="534" height="305"/>

and Mac  
<img src="./Images/v1_1_0_Mac.png" alt="Windows" width="534" height="305"/>

## Thanks to:
Everyone that contributed to the many Stardot forum threads.

A big shout out to Matt Godbolt and jsbeeb.  
This is not because I pinched any of his code but because it is such an accessible emulator.  
I can't count the number of times I've single stepped through some test program or another in the jsbeeb debugger looking for where BSharp deviated.

## Release History
Releases can be found in the IJCalypso/BSharpReleases repository.  
They are standalone so can be run from the directory that the zip file is extracted to without needing any additional installation.

MacOS will probably block execution as the files are from an unknown source. If you wish to circumvent this it will be necessary to open a Terminal window and issue the command: xattr -cr path_to_folder.

**v1.1.0 : 10/10/2026**  
Added the ability to select between two keyboard maps.  
Native:  
Matches the actual keyboard layout closely. In order to avoid cases where there is a shifted key that is unshifted on the Beeb and vice-versa there are a few changes. "=" and "_" are swapped. "'" and ":" are swapped. "^" is swapped with whatever is the unshifted key under "~". That is "#" on a Windows keyboard and "`" on a Mac keyboard.  
Positional:  
Tries to match the Beeb keyboard layout as closely as possible. Due to the number of keys and their layout there are a few changes. "\ |" is next to the left Shift key. "\_ £" is next to the 1 key.  
Shift Lock is not modelled, Caps Lock is the key to the left of Space, Del and Copy are the two keys to the right of Space.
This is for the convenience of my own laptops so I don't know if it will suit everybody.  

**v1.0.2 : 08/10/2026**  
Modified scheduler to cope with newer, faster CPUs. I bought a new laptop.  
Minor bug fixes.  
Cosmetic code changes to agree with ReSharper rules.

**v1.0.1 : 05/06/2026**  
Performance improvements in methods highlighted as high cpu users by PerfView.

**v1.0.0 : 29/05/2026**  
BBC Model B emulation with a 2MHz 6502A cpu and 3MHz 65C02 co-processor.  
BBC Master 128 emulation with a 2MHz 65C02 cpu and 4MHz 65C02 co-processor.  
1770 disk emulation - 8271 not emulated.  
DFS and ADFS supported for read and write.  
Tape reading supported (good enough to load Nightshade anyway).  
Serial writing supported (*FX3,5 will send output to the BSharpAcia.bin file).  
USB analogue joystick supported (If set up in DS4 mode).  
