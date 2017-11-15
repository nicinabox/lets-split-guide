# Assembly

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [Helpful references](#helpful-references)
- [Parts](#parts)
- [Cost Breakdown](#cost-breakdown)
- [Order the case](#order-the-case)
- [Mount the sockets](#mount-the-sockets)
- [Mount the Diodes](#mount-the-diodes)
- [Mount Header Pins](#mount-header-pins)
- [Mount the Pro Micro](#mount-the-pro-micro)
  - [Mount the Pro Micro the Right Way](#mount-the-pro-micro-the-right-way)
- [Assemble the case **PLATE CASE HASN'T BEEN TESTED WITH SOCKET VERSION**](#assemble-the-case-plate-case-hasnt-been-tested-with-socket-version)
- [Finishing touches](#finishing-touches)
- [Troubleshooting](#troubleshooting)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Helpful references

- [/u/wootpatoot's v2 assembly instructions](https://www.reddit.com/r/MechanicalKeyboards/comments/5funsl/guidelets_split_v2_assembly_instructions/)
- [/u/bakingpy's build log](https://www.reddit.com/r/MechanicalKeyboards/comments/5rgj06/lets_split_v2_build_log_with_mini_usb_pro_micro/)
- [/u/tobiasboon's Let's split v2 build log (with I2C)](https://www.reddit.com/r/MechanicalKeyboards/comments/5s3yr2/lets_split_v2_build_log_with_i2c_photos/)

## Parts

At the writing of this guide, the PCBs come with connectors presoldered, and with diodes and sockets provided.

- [ ] Socket PCB - [You will need a set of (2) PCBs](getting-pcbs.md)

- [ ] **2** 5V/16MHz Pro Micros ([official](https://www.sparkfun.com/products/12640) or [clone](https://www.ebay.com/sch/i.html?_from=R40&_sacat=0&_nkw=Arduino+Micro+Pro+ATmega32U4+5V&rt=nc&LH_BIN=1))
- [ ] **48** [Switches of your choice](https://mechanicalkeyboards.com/shop/index.php?l=product_list&c=107)
- [ ] [TRRS cable](https://www.amazon.com/gp/product/B019TRW4HQ/ref=oh_aui_detailpage_o04_s00?ie=UTF8&psc=1)

## Cost Breakdown

| Cost | Part |
|:--|:--|
| $40 | PCB |
| $10-60 | Pro Micros |
| $36 | Plate and case |
| $9 | Standoffs |
| $9 | Screws |
| $7 | TRRS cable |
| $14-50 | Switches |

**Total cost: ~$125-211**. Yours might be more or less depending on the exact parts you source, what you already have, and shipping costs.


## Order the case

Section yet to be filled. 

## Mount the sockets

First thing to do, is to mount the sockets, as these benefit from having the front side of the PCB entirely flat.
Place the PCB down with the connectors facing up, and begin inserting a socket into each switch position, making sure to like them up with the pads.
![](images/socket-version/sockets.jpg)


## Mount the Diodes

Diodes allow current to flow in one direction only. Mount the diodes with the black line facing the square pad.

![](images/socket-version/diodes.jpg)

On the socket version, the connectors are premounted to have two similar connectors on the inside. Usually the TRRS connector

All parts on the socket version are put on the backside of the PCB.

If you are getting a plate case lasercut, it can be very beneficial to have a small piece of acrylic cut, that is 7.5mm across.  
This can be used to form the diode leads around. One such model is available [here](https://cad.onshape.com/documents/c6e5ae250d1e24fe46c9ef6c/w/d69f7049c0921df3d2b241f9/e/6be47f68dae3db6d2d56add6)

Otherwise bend the diodes manually by using a small book binding or small pair of pliers to gently make a 90 degree bend on each side of the diode. It might take a few tries to get right, but you'll get the hang of it soon. They should drop easily into the 2 holes.

**Double check your work**. Black lines should be facing the square pad.

> *Tip:* **Lightly** tack each diode in from the top. This will keep them snug against the surface once we flip it over and do the real soldering from the bottom. You only need a tiny amount of solder here and you should still be able to see through the hole.

**SPECIAL NOTE ON THE PROTOTYPE SOCKET BOARDS, THE** The bottom row of the diodes will be poking out right under the switches. Because of this these dioes cannot poke through the PCB, and have to be cut flush with the front of the PCB before final soldering.

Flip your PCB over and solder the diodes then snip the excess leads.

## Mount Header Pins

You should have received header pins with your Pro Micro. Due to the placement of the headers, these can't stick out the other side of the PCB either, you will therefore have to push down the black plastic that holds the pins together, such that the pins are flush with the front side.

**Images:**
![One](images/socket-version/shorten-headers/1.png)
![Two](images/socket-version/shorten-headers/2.png)
![Three](images/socket-version/shorten-headers/3.png)
![Four](images/socket-version/shorten-headers/4.png)

Insert the short side into the bottom of PCB, again. All components are inserted on the same side of the PCB

> *Tip:* To keep them aligned you can slip the Pro Micro over the pins but **do not solder the Pro Micro at this time**.

Tack the pins on the end and inspect. If the pins are not quite aligned with the board, heat one side with your iron and press it in. It should make a satisfactory "click".

Solder the rest of the pins (it won't take much solder here).

The long part of the pins should be protruding from the bottom. We'll trim these later after soldering the Pro Micro, but you can leave them be for now.

## Mount the Pro Micro

> *Tip:* Flash your Pro Micro now before you mount it. You can test it by using a multimeter to measure the voltage between VCC and RAW. It should be around 5V. If it's bad it'll be a lot less headache than desoldering.

### Mount the Pro Micro the Right Way

You'll be working from the bottom of the board for this step.

- On the **left PCB** the Pro Micro should be **smooth side up** (facing you)
- On the **right PCB** the Pro Micro should be **component side up** (facing you)

The micro USB of the Pro micro should be facing the mini USB of the PCB

![](http://i.imgur.com/r4kMBSF.jpg)

You may need to **Place a bit of tape over the sockets under the pro micro** as they might touch the controller and cause issues.

On the left PCB, make sure the micro USB cable can fit in the socket, before soldering in the Pro Micro.

** Clearance with plates hasn't been tested with this socket version. Feed-back would be much appreciated **

Ensure the orientation of your controllers are correct and you've already soldered the 2 sockets underneath, then solder all the pins on the Pro Micro.

At this point you should be able to plug in and verify that the Arduino is working.

Trim the excess from the header pins.

![](http://i.imgur.com/WOOB0nr.jpg)

## Assemble the case **PLATE CASE HASN'T BEEN TESTED WITH SOCKET VERSION**

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