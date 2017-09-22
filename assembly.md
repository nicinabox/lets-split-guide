# Assembly

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [Helpful references](#helpful-references)
- [Parts](#parts)
- [Cost Breakdown](#cost-breakdown)
- [Order the case](#order-the-case)
- [Mount the Diodes](#mount-the-diodes)
- [Mount the TRRS Jack](#mount-the-trrs-jack)
- [Connect Jumpers](#connect-jumpers)
- [Mount Header Pins](#mount-header-pins)
- [Mount the Pro Micro](#mount-the-pro-micro)
  - [Mount the 2 switches under the Pro Micro](#mount-the-2-switches-under-the-pro-micro)
  - [Mount the Pro Micro the Right Way](#mount-the-pro-micro-the-right-way)
- [Mount the rest of the switches](#mount-the-rest-of-the-switches)
- [Assemble the case](#assemble-the-case)
- [Finishing touches](#finishing-touches)
- [Troubleshooting](#troubleshooting)
  - [Column 2 or column 5 doesn't work (under the controller)](#column-2-or-column-5-doesnt-work-under-the-controller)
  - [One side isn't working](#one-side-isnt-working)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Helpful references

- [/u/wootpatoot's v2 assembly instructions](https://www.reddit.com/r/MechanicalKeyboards/comments/5funsl/guidelets_split_v2_assembly_instructions/)
- [/u/bakingpy's build log](https://www.reddit.com/r/MechanicalKeyboards/comments/5rgj06/lets_split_v2_build_log_with_mini_usb_pro_micro/)
- [/u/tobiasboon's Let's split v2 build log (with I2C)](https://www.reddit.com/r/MechanicalKeyboards/comments/5s3yr2/lets_split_v2_build_log_with_i2c_photos/)

## Parts

- [ ] v2 PCB - [You will need a set of (2) PCBs](getting-pcbs.md)

- [ ] **2** 5V/16MHz Pro Micros ([official](https://www.sparkfun.com/products/12640) or [clone](http://www.ebay.com/itm/Arduino-Pro-Micro-ATmega32U4-5V-16MHz-Replace-ATmega328-Pro-Mini-Leonardo-USB-/222383274330?hash=item33c713795a:g:3CkAAOSwubRXMmnp))
- [ ] **48** 1N4148 diodes ([1N4148FS-ND](https://www.digikey.com/products/en?keywords=1N4148FS-ND), just go ahead and get 100)
- [ ] **2** TRRS jacks ([CP-43514-ND](https://www.digikey.com/product-detail/en/cui-inc/SJ-43514/CP-43514-ND/368146))
- [ ] [Plate & case](http://qmk.fm/keyboards/lets_split/lets_split_laser.svg) (sandwich design)
- [ ] **8** [10mm M3 standoffs](https://www.mcmaster.com/#94868A166) (required for sandwich case)
- [ ] **16** [6mm M3 screws](https://www.mcmaster.com/#92095a179/=16e985x) (required for sandwich case, comes in packs of 100)
- [ ] **48** [Switches of your choice](https://mechanicalkeyboards.com/shop/index.php?l=product_list&c=107)
- [ ] [TRRS cable](https://www.amazon.com/gp/product/B019TRW4HQ/ref=oh_aui_detailpage_o04_s00?ie=UTF8&psc=1)

**/!\** The M3 screws linked above may have a slight clearance issue with the keycap. You can countersink the head or use a screw with a lower profile head. I'm testing out button head screws to see if they work better.

## Cost Breakdown

| Cost | Part |
|:--|:--|
| $10 | PCB |
| $10-60 | Pro Micros |
| $3 | Diodes |
| $2 | TRRS Jack |
| $36 | Plate and case |
| $9 | Standoffs |
| $9 | Screws |
| $7 | TRRS cable |
| $14-50 | Switches |

**Total cost: ~$100-186**. Yours might be more or less depending on the exact parts you source, what you already have, and shipping costs.

## Order the case

*Optional if you have your own plate and case.*

Download the raw plate SVG from Github (Alt-click **Raw** should do it).

Head over to [Ponoko](https://www.ponoko.com/) and create an account if it's your first time.

1. Click **My Designs** > **Overview** > **Add a new design**
2. Click **Upload your design** and select the `letssplitv2.svg` file
3. Click **Add this design**
4. Set the Quantity to 2 (the design is only 1 side)
5. Click **Add Materials** > **Add a Material**
6. Select **Choose a material type** > **Plastic**
7. Select **Choose a material** > **Acrylic - Clear - Antistatic** (You can choose whatever type of material you like. We'll be using Acrylic for this build.)
8. Select **Choose a thickness** > **0.118 inches**
9. Select **Choose a size** > **P1 - 7.126 inches long x 7.126 inches wide**
10. Click **Add this material**
11. Your total should be around $36
12. Click **Make it** and complete the order process

## Mount the Diodes

Diodes allow current to flow in one direction only. Mount the diodes with the black line facing the square pad.

![](http://i.imgur.com/uJPqbiB.jpg)

You'll want to determine the orientation of your boards right now. Remember, they're symmetrical, but you can set it up to have your TRRS jacks on the inside or on the same side (right or left). For this build we'll be mounting our TRRS jacks on the inside, closest to one another.

- The **left PCB** will have the **TRRS jack on the right**
- The **right PCB** will have the **TRRS jack on the left**

This orientation will determine the top of your PCB. Insert the diodes on the top. Once mounted they will fit between the PCB and the plate.

> *Tip:* Although it doesn't actually matter which side you mount the diodes on so long as they're in the correct orientation, there are several factors that may influence which side you choose. If you have a 3mm acrylic plate, it is desirable to mount them on the top side to help reinforce the gap and prevent the switches from rising up with the PCB. If you have a 5mm acrylic plate, it is mandatory to mount them on the bottom side for the plate to fit. If it is left up to choice, it can be beneficial to mount them on the bottom side to allow for future desoldering replacement should a there be some type of failure. For this build we'll put them on top.

Use a helping hand tool to hold the PCB above your work surface.

Use a small book binding or small pair of pliers to gently make a 90 degree bend on each side of the diode. It might take a few tries to get right, but you'll get the hang of it soon. They should drop easily into the 2 holes.

**Double check your work**. Black lines should be facing the square pad.

> *Tip:* **Lightly** tack each diode in from the top. This will keep them snug against the surface once we flip it over and do the real soldering from the bottom. You only need a tiny amount of solder here and you should still be able to see through the hole.

Flip your PCB over and solder the diodes then snip the excess leads.

## Mount the TRRS Jack

Mount the TRRS jack on the side opposite from your diodes. It should be on the bottom.

> *Tip:* Use masking tape or a spare finger to hold it in place while you solder it. Tack a couple pins and make sure it's snug against the board, then do the rest.

## Connect Jumpers

On the **underside** of the PCB, right below the TRRS jack, you'll see two sets of 3 pads labelled VCC and GND. Jumper them like this:

```
VCC [x]     [ ] VCC
    [x]     [x]
GND [ ]     [x] GND
```

Do both PCBs the same.

![](http://i.imgur.com/eLRUJxA.jpg)

## Mount Header Pins

You should have received header pins with your Pro Micro. Insert the short side into the bottom of PCB (same side as the TRRS jack) and solder them in.

> *Tip:* To keep them aligned you can slip the Pro Micro over the pins but **do not solder the Pro Micro at this time**.

Tack the pins on the end and inspect. If the pins are not quite aligned with the board, heat one side with your iron and press it in. It should make a satisfactory "click".

Solder the rest of the pins (it won't take much solder here).

The long part of the pins should be protruding from the bottom. We'll trim these later after soldering the Pro Micro, but you can leave them be for now.

## Mount the Pro Micro

**Pay special attention on this step**. There are several things that need to be done in the right order and orientation.

> *Tip:* Flash your Pro Micro now before you mount it. You can test it by using a multimeter to measure the voltage between VCC and RAW. It should be around 5V. If it's bad it'll be a lot less headache than desoldering.

### Mount the 2 switches under the Pro Micro

> *Heads up:* The plate design linked in this build is not symmetrical. One edge is slightly smaller than the other. You probably want the small edge towards the center of the board.

1. Grab 2 switches and your top plate (That's 2 switches for each side)
2. Snap the switches into your plate in the spots that overlay the Pro Micro (on the left side that's column 2, and on the right that's column 5).
3. Line up your PCB with the switches and solder them between the header pins

### Mount the Pro Micro the Right Way

You'll be working from the bottom of the board for this step.

- On the **left PCB** the Pro Micro should be **smooth side up** (facing you)
- On the **right PCB** the Pro Micro should be **component side up** (facing you)

![](http://i.imgur.com/r4kMBSF.jpg)

You may need to **trim the pins on the left side switches** as they will likely touch the controller and prevent it from resting flush with the pins.

**Clearance is going to be tight on the right side** between the USB and the bottom of the plate, so make sure you've got it as snug as possible against the header pins.

Ensure the orientation of your controllers are correct and you've already soldered the 2 switches underneath, then solder all the pins on the Pro Micro.

At this point you should be able to plug in and verify the board is working and the two mounted switches should work (if you already flashed). If it is, great job!

Trim the excess from the header pins.

![](http://i.imgur.com/WOOB0nr.jpg)

## Mount the rest of the switches

Home stretch. Gently snap in the rest of the switches and solder them.

![](http://i.imgur.com/GFF0sd7.jpg)

## Assemble the case

1. Insert the screws on top
2. Screw the standoffs onto the top screws
3. Line up the bottom of the case with the standoffs
4. Screw in the bottom screws to the standoffs

![](http://i.imgur.com/coW4MsQ.jpg)
> *Tip:* Finger tight is sufficient, but you can snug them down just a tad with a tool. Be easy, they don't need much!

## Finishing touches

1. Add some adhesive vinyl pads to the bottom
2. Install your keycaps and connect the two halves with the TRRS cable.

You did it! Great job!

## Troubleshooting

### Column 2 or column 5 doesn't work (under the controller)

If you're having trouble with a dead column right over your Pro Micro it could be that you've got a short from the switch pins. Try to get under there and bend them down.

### One side isn't working

- Double check your jumpers are bridged correctly.
- Make sure J1 on the Pro Micro is **not** bridged.
