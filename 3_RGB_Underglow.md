# Let's Split RGB Underlgow

![](http://i.imgur.com/qFXhuu1.jpg)

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
## Contents

- [Parts](#parts)
- [Prep the strips](#prep-the-strips)
- [Prep the wire](#prep-the-wire)
- [Connect to the Pro Micro](#connect-to-the-pro-micro)
- [Sync across sides](#sync-across-sides)
- [QMK](#qmk)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Parts

- [ ] [WS2812 LED strip](https://www.sparkfun.com/products/12025)
- [ ] 24 AWG (or smaller) stranded wire in 3 colors (white, red, black are good choices)

The WS2812B strip is also fine, but avoid the sealed waterproof one for keyboards.

Look for a strip with spaced, 3-pad connectors. When you cut between them the pads are bigger and it's easier to solder to. Example:

![](http://i.imgur.com/bwrhq7p.jpg)

## Prep the strips

1. Cut 2 5-LED segments from the WS2812 strip (cut between the pads, or in the middle of the pads if you don't have a space between)
2. Fill the pads on both ends with solder like the picture below

Avoid buying LED strips like this one where you cut the pad in half.  There's just not much left to solder to, but it can be done.

![](http://i.imgur.com/70IHyql.jpg)

## Prep the wire

1. Cut **3 white**, **3 red**, and **3 black wires**, about 5cm (2in) in length
2. Strip the ends about 2-3mm
3. Solder the wires on each end of the strip
	- White: VCC
	- Red: DIN/DO
	- Black: GND

## Connect to the Pro Micro

Remember, current only flows one way through diodes so be sure you've got your LED strip in the correct orientation.

Data goes like this: `--> Data In (DIN) --> Data Out (DO)`

On the Pro Micro you connect the USB cable to:

1. Connect LED **DIN to TX0 pin**
2. Connect LED **GND to any GND pin**
3. Connect LED **VCC to VCC pin**

> *Tip:* You may need to adjust the length of some of your wiring so it routes snugly to the board.

![](http://i.imgur.com/iHpC27N.jpg)

## Sync across sides

Remember those jumpers we did before below the TRRS jack? We're going Use the 3rd pad here.

On the DO side of the controlled strip:

1. Connect LED **GND to GND pad**
2. Connect LED **VCC to VCC pad**
3. Connect **DO to Extra Data**. It's a through hole right between the VCC/GND pads.

> *Tip:* These pads are pretty small so be careful not to mess up your jumpers.

![](http://i.imgur.com/qOv7qNQ.jpg)

On the other side:

1. Connect to **VCC, GND, and Extra Data to DIN pad** on the strip.
2. Don't connect the DO side

![](http://i.imgur.com/1IKhZG5.jpg)

Your wiring should look like this:

```
TX0 -> DIN -> DO -> extra data -> (TRRS to other side) -> extra data -> DIN
```

![](http://i.imgur.com/mSypC5y.jpg)

## QMK

- [QMK underglow docs](https://github.com/qmk/qmk_firmware/wiki#rgb-under-glow-mod)
- [LS config for reference (recommended)](https://github.com/nicinabox/qmk_firmware/tree/nic/keyboards/lets_split/keymaps/nic)

---

1. Add a `Makefile` and `config.h` to your keymap if you don't already have one.
2. In the Makefile add `RGBLIGHT_ENABLE = yes`
3. Add a layer to control the RGB lights
4. In `config.h`:

```
#undef RGBLED_NUM
#define RGBLIGHT_ANIMATIONS
#define RGBLED_NUM 10
```

Now flash that sucker and turn your lights on.
