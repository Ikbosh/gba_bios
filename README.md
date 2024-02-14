This code can be used to compile a GBA BIOS ROM that's more compatible with various ROM Hacks. Based on the work of;

## CAMTHESAXMAN [github](https://github.com/camthesaxman/gba_bios)
## AMMRAT13 [github](https://github.com/ammrat13/gba_bios)
## NORMMATT [github](https://github.com/Normmatt/gba_bios)
## PIKALAXALT [github](https://github.com/PikalaxALT/gba_bios)

As various pull requests and patchs were done at different branches by the aforementioned parties, I have attempted to join all of them in one location - in the hopes it's the most useful BIOS ROM. I don't have the ability to test it, or truly understand what I'm working with; so YMMV. I won't be able to fix things if any issues arise, can only help compiling on it and can if necessary see if whatever ROM you're using works for my compiled version.

Various Requirements:
[devkitARM](http://devkitpro.org/wiki/Getting_Started/devkitARM) is required to assemble the ROM.

Because not all of it has been disassembled yet, an original BIOS is required in order to build. Place the original BIOS ROM in the root directory of "gba_bios" and rename this file to baserom.bin.

You may also need (if not familiar with building code like this various other parts relevant to your operating system. As an example; here's the code needed to run on a fresh debian system to successfully compile the ROM. Please ensure you amend the WGET Command with a URL that contains the original GBA BIOS ROM.

```
apt install build-essential gcc-arm-none-eabi git libpng-dev
export PATH="/Applications/ARM/bin:$PATH"
wget https://apt.devkitpro.org/install-devkitpro-pacman
chmod +x ./install-devkitpro-pacman
./install-devkitpro-pacman
dkp-pacman -Syu gba-dev
cd gba_bios
chmod +x build_tools.sh
./build_tools.sh
wget -O baserom.bin https://url_to_GBA_BIOS_ROM/gba_bios.bin
make
```
