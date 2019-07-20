# NixOS on the Marvell ESPRESSObin
http://espressobin.net/

## My board
I have an V7 1GB board.

It boots with the stock `espressobin-bootloader-cpu-1000-ddr4-1cs-1g-atf-g39a62a1-uboot-g255b9cc-20181107-REL.bin`

## U-boot
Hacky way to build: link u-boot as an overlay, then run `nix build -f channel:nixos-unstable pkgsCross.aarch64-multiplatform.ubootEspressobinImages`.

The Armbian project has built U-Boot 18.03 images: https://dl.armbian.com/espressobin/u-boot/

### Links
- Bootloader build instructions: http://wiki.espressobin.net/tiki-index.php?page=Build+From+Source+-+Bootloader
- Forum post about building and flashing U-boot: http://espressobin.net/forums/topic/how-to-flash-u-boot/
- A mailing list thread complaining about how ridiculous the bootloader build process is: https://lists.debian.org/debian-arm/2018/08/msg00014.html
- Implies upstream U-Boot supports Espressobin, maybe they mean Marvell's fork does (and maybe only v5): http://espressobin.net/forums/topic/how-to-flash-u-boot/
- An issue about adding distro config support to Marvell's U-boot fork: https://github.com/MarvellEmbeddedProcessors/u-boot-marvell/issues/3
- A poor single mailing list post about trying to make upstream U-Boot work (mentioned in a comment in the previous link): https://lists.denx.de/pipermail/u-boot/2018-August/339362.html
- Someone trying newer U-boot, includes build command: https://github.com/MarvellEmbeddedProcessors/atf-marvell/issues/12
- Someone's step-by-step build process: https://lists.denx.de/pipermail/u-boot//2017-July/298761.html
- MACCHIATObin U-boot build instructions, which seem to use the newer build process with mv-ddr-marvell: http://wiki.macchiatobin.net/tiki-index.php?page=Build+from+source+-+Bootloader
- Someone saying those instructions don't work and a fix: https://macchiatobin.net/forums/topic/u-boot-build-instruction-do-not-lead-to-usable-image/
- Armbian, 18.12 release Marvell stuff: https://forum.armbian.com/topic/9142-marvell-issued-armada-lsp-release-1812-to-general-public/
