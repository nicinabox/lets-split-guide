# Flashing

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [Which side do I flash?](#which-side-do-i-flash)
- [Windows](#windows)
- [OSX, Linux](#osx-linux)
  - [Build Keymap (QMK)](#build-keymap-qmk)
  - [Bootloader](#bootloader)
  - [Flash](#flash)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Which side do I flash?

See the QMK firmware section on [Flashing](https://github.com/qmk/qmk_firmware/tree/master/keyboards/lets_split#flashing) for an up to date explanation.

## Windows

See [/u/CampAsAChamp's Windows Guide](https://github.com/CampAsAChamp/LetsSplitWindowsGuide)

## OSX, Linux

### Build Keymap (QMK)

From the qmk_firmware directory:

```
make lets_split-rev2-YOUR_KEYMAP_NAME-avrdude
```

Don't forget to replace `YOUR_KEYMAP_NAME` with the actual name of your keymap.

You'll now have a .hex file that we can use to flash.

### Bootloader

Connect RST and GND to enter bootloader. If you're using an official Sparkfun Pro Micro (the red one) you need to short this twice quickly.

You will have 8 seconds to flash before it continues on to the sketch.

> Tip: If this is the first time the Pro Micro has been flashed it should go directly to the bootloader on start.

### Flash

QMK now includes a very easy way to automatically find the serial port and flash without having to race the bootloader. From the qmk directory type (`$` indicates the prompt. Don't type that):

```
$ make lets_split-rev2-YOUR_KEYMAP_NAME-avrdude
```

Be sure to replace `YOUR_KEYMAP_NAME` with the name of your keymap.

Example:

```bash
$ make lets_split-rev2-YOUR_KEYMAP_NAME-avrdude
Reset your Pro Micro now

Connecting to programmer: .
Found programmer: Id = "CATERIN"; type = S
    Software Version = 1.0; No Hardware Version given.
Programmer supports auto addr increment.
Programmer supports buffered memory access with buffersize=128 bytes.

# [snip]

avrdude: verifying ...
avrdude: 22286 bytes of flash verified

avrdude: safemode: Fuses OK (E:CB, H:D8, L:FF)

avrdude done.  Thank you.
```
