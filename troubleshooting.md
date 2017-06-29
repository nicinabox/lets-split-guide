# Troubleshooting

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
- [Troubleshooting](#troubleshooting)

- [Assembly](#assembly)
  - [Column 2 or column 5 doesn't work (under the controller)](#column-2-or-column-5-doesnt-work-under-the-controller)
  - [One side isn't working](#one-side-isnt-working)
- [Flashing](#flashing)
  - [Programmer not responding](#programmer-not-responding)
  - [Can't open device](#cant-open-device)
  - [Your right side has the TRRS on the LEFT and the keymap is reversed](#your-right-side-has-the-trrs-on-the-left-and-the-keymap-is-reversed)
  - [Your right side has the TRRS on the RIGHT and the keymap is reversed](#your-right-side-has-the-trrs-on-the-right-and-the-keymap-is-reversed)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Assembly

### Column 2 or column 5 doesn't work (under the controller)

If you're having trouble with a dead column right over your Pro Micro it could be that you've got a short from the switch pins. Try to get under there and bend them down.

### One side isn't working

- Double check your jumpers are bridged correctly.
- Make sure J1 on the Pro Micro is **not** bridged.
- Make sure you're using a TRRS cable, not a TRS cable



## Flashing

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
