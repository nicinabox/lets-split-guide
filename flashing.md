# Flashing

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [Windows](#windows)
- [Which side do I flash?](#which-side-do-i-flash)
- [OSX, Linux](#osx-linux)
  - [Build Keymap (QMK)](#build-keymap-qmk)
  - [Bootloader](#bootloader)
  - [Flash](#flash)
- [Troubleshooting](#troubleshooting)
  - [Programmer not responding](#programmer-not-responding)
  - [Can't open device](#cant-open-device)
  - [Your right side has the TRRS on the LEFT and the keymap is reversed](#your-right-side-has-the-trrs-on-the-left-and-the-keymap-is-reversed)
  - [Your right side has the TRRS on the RIGHT and the keymap is reversed](#your-right-side-has-the-trrs-on-the-right-and-the-keymap-is-reversed)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Which side do I flash?

See the QMK firmware section on [Flashing](https://github.com/qmk/qmk_firmware/tree/master/keyboards/lets_split#flashing) for an up to date explanation.

## Windows

See [/u/CampAsAChamp's Windows Guide](https://github.com/CampAsAChamp/LetsSplitWindowsGuide)

## OSX, Linux

### Build Keymap (QMK)

From the lets_split directory:

```
make rev2-YOUR_KEYMAP_NAME-avrdude
```

Don't forget to replace `YOUR_KEYMAP_NAME` with the actual name of your keymap.

You'll now have a .hex file that we can use to flash.

### Bootloader

Connect RST and GND to enter bootloader. If you're using an official Sparkfun Pro Micro (the red one) you need to short this twice quickly.

You will have 8 seconds to flash before it continues on to the sketch.

> Tip: If this is the first time the Pro Micro has been flashed it should go directly to the bootloader on start.

### Flash

QMK now includes a very easy way to automatically find the serial port and flash without having to race the bootloader. From the keymap directory type (`$` indicates the prompt. Don't type that):

```
$ make rev2-YOUR_KEYMAP_NAME-avrdude
```

Be sure to replace `YOUR_KEYMAP_NAME` with the name of your keymap.

Example:

```bash
$ make rev2-YOUR_KEYMAP_NAME-avrdude
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

## Troubleshooting

### Programmer not responding

The controller isn't in bootloader mode. You may have missed the 8 second window to flash.

### Can't open device

The serial port you specified isn't the one the controller is using.

### Your right side has the TRRS on the LEFT and the keymap is reversed

As of Feb 7, 2017 this should no longer be necessary. The default `rev2` orientation matches the keymap below.

You need to flip the keymap in QMK to match the orientation of your board. If you have the right side setup with the TRRS on the left you'll need to reverse the keymap for that side.

Add a new file to your keymap directory named `flip_keymap.h`:
```
#undef KEYMAP
#define KEYMAP( \
	k00, k01, k02, k03, k04, k05, k45, k44, k43, k42, k41, k40, \
  k10, k11, k12, k13, k14, k15, k55, k54, k53, k52, k51, k50, \
  k20, k21, k22, k23, k24, k25, k65, k64, k63, k62, k61, k60, \
  k30, k31, k32, k33, k34, k35, k75, k74, k73, k72, k71, k70 \
	) \
	{ \
		{ k00, k01, k02, k03, k04, k05 }, \
		{ k10, k11, k12, k13, k14, k15 }, \
		{ k20, k21, k22, k23, k24, k25 }, \
		{ k30, k31, k32, k33, k34, k35 }, \
		{ k40, k41, k42, k43, k44, k45 }, \
		{ k50, k51, k52, k53, k54, k55 }, \
		{ k60, k61, k62, k63, k64, k65 }, \
		{ k70, k71, k72, k73, k74, k75 } \
	}
```

Then include this file at the top of `keymap.c` under `#include "lets_split.h"`:

```
#include "flip_keymap.h"
```

### Your right side has the TRRS on the RIGHT and the keymap is reversed

Use `rev2fliphalf` instead of `rev2` as the target.
