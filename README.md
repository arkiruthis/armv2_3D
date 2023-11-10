# armv2_3D

### Description
A small fixed-point 3D mesh renderer for Acorn Archimedes. Written in C89 and ARM assembly. Utilizes the [C89 dynamic array](https://github.com/eteran/c-vector) by Evan Teran.

Primarily aimed at ARM250 (A3010 / A3020) but code compatible up to RISC PC.

As per the license this software is released AS IS. I don't have the time to look through pull requests, etc., but please feel free to fork the project and play with it as you will. :)

[![IMAGE ALT TEXT](http://img.youtube.com/vi/HoJ2emDg2gI/0.jpg)](http://www.youtube.com/watch?v=HoJ2emDg2gI "Video Title")

### Prerequisites
- RPCEmu or Arculator (NOTE - Arculator needs UniBoot for Acorn make tools to be located)
- Acorn C++ 

### QuickStart
1. Checkout the repo and copy the `Project` folder into your `hostfs` folder for your emulator.
2. At the desktop, open the Acorn C++ tools folder. `$HostFS::HostFS.$.AcornC_C++.Tools`
3. Open the Projects folder.
4. Double-click the Makefile to generate the `!MeshRenderer` executable.
5. Run the generated `!Run` script (which sets some environment variables) to launch.

### Controls
F1 - F4: Set Color palette.
SPACEBAR: Stop/Start rotation.
NUMPAD: 4/6 (Heading), 8/2 (Pitch), 7/9 (Roll)

### Implementation notes
This currently uses a very naive rasterizer which renders up to a 4-byte word boundary and then uses STMIA with 4 registers to store 16-bytes of color at a time. This is by no means the fastest way to to do this.

### Running on Original Hardware
Use an emulator (Arculator, RPCEmu, ArchiEmu, etc.) to copy the Projects folder onto an ADF and either use that in a Gotek, or use it to prepare a floppy disk. This is to preserve the file types that are set up on HostFS so that they run correctly on native RISCOS. 

### Thanks

I'm deeply grateful to the community on the [Stardot forums](https://stardot.org.uk/forums) who have offered valuable assistance and patiently offered answers to my endless questions. 

Gustavo Pezzi [(pikuma)](https://pikuma.com/) - For their superb course on 3D Graphics Programming which provided much needed insight for this project.

Julien Verneuil - For their [fantastic online blog post](https://www.onirom.fr/wiki/blog/30-04-2022_Archimedes-ARM2-Graphics-Programming/) about Archimedes graphics programming. Some great Voxel terrain examples there as well.

ray//.tSCc. - For this fascinating [2005 demo coding article](http://alive.atari.org/alive11/frstclip.php) which provided a much better radix sort alternative to qsort() for speeding up the triangle depth pass.

RISCOS.com for making available online much of the [documentation](http://www.riscos.com/support/developers/) that was orginally only available in book form.

David Ruck for his superb TimerMod utility which is [available from his site](https://armclub.org.uk/free/) which made profiling many of the routines far easier.

### Book References

- "3D Math Primer for Graphics and Game Development" - Fletcher Dunn and Ian Parberry.
- "3D Computer Graphics" - Dr Alan Watt
- "Programmer's Reference Manual" - Acorn
- "Archimedes Assembly Langauage" - Mike Ginns



