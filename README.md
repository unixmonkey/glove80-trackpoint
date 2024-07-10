# glove80-trackpoint
Trackpoint sidecar mod for the Glove80 keyboard

## Why

I recently started getting RSI-like pain and went on a deep dive into the word of ergonomic split keyboards, but I knew part of my issue was my mouse usage habits, and that moving from the keyboard to the mouse (or trackpad) over and over again certainly wasn't helping.

Unfortunately, there currently are almost no commercially available keyboards that have built-in pointing devices.
However, the [MoErgo Glove80](https://www.moergo.com/collections/glove80-keyboards) keyboard tries to be highly ergonomic, as well as [customizable](https://www.moergo.com/pages/glove80-ergonomic-keyboard-customization) platform, and even provides built-in anchor points and some basic 3d models that can be used to add your own pointing devices right between the thumb cluster and forefinger areas.

So I bought the Glove80, and a 3d printer, and got to work. This is helping me, and so I help my efforts can help others.

## What you'll need

1. The MoErgo Glove80 keyboard
2. Soldering equipment, some wire, and a steady hand
3. A hot glue gun (or regular glue/tape could work in a pinch)
4. A 3D printer (or a friend/library/makerspace/business with one)
5. [USB Overdrive](https://www.usboverdrive.com/) or an equivalent software that allows you to invert x and y axis of your mouse (ideally per-device)
6. Trackpoint / Rocker mouse control board (I used [this one](https://www.aliexpress.us/item/3256804502547098.html)
7. 2.5mm screws. I'm using 8mm deep ones I got in [this kit](https://www.amazon.com/dp/B0BLCFD9HR)
8. A USB-C breakout board (I used [this treedix board](https://treedix.com/products/treedix-4pcs-usb-type-c-breakout-board-serial-basic-breakout-female-connector-type-pcb-converter-board) also available on [Amazon here](https://www.amazon.com/dp/B096M2HQLK), but this is completely optional. I used it because I wanted to be able to "unplug" at the keyboard, instead of at the computer.
9. These [3d model files](/models/)

## Test the trackpoint

While unlikely, it's entirely possible the trackpoint may be DOA, so plug it in and make sure it works before we start questioning our sanity if it stops after hacking it apart.

## Soldering

The trackpoint rocker board (blue) comes pre-soldered onto the control board (green), but together they are too big (in my opinion) to get the trackpoint really close enough to comfortably reach, so let's de-solder that, and re-solder the 2 parts together using some wire instead. Be sure to solder on the BACK side of the blue board, or you'll have trouble with the trackpoint being flush when mounted to the case.

These contacts are very close to each other, so be careful your solder and wires doesn't bridge from one solder point to it's neighboring ones. If it does, de-solder and try again. Once finished, plug it in and make sure it still works. If it does, I recommend hot-gluing the wires in place, and testing again.

Assuming that went well, the next step is to add the USB-C connector (if desired). First take a photo of the wires to make sure you know what color goes where. Here's mine if you forgot:

The Trackpoint only uses 4 pins on it's built-in cable, and the Treedix connector has 6. The red wire is power (VBUS), the black wire is ground (GND), the blue wire is Data - (D-), and the green wire is data + (D+). Solder your wires onto the top surface. There are little holes so you can push your wires though before soldering them in place.

Again, I recommend testing things when done to make sure wiggling the trackpoint moves the mouse at this point, and possibly hot-gluing over the connection if it's good.

## 3d printing

This model should serve as a ready-to-print piece for you, however, I've made some design tweaks over the MoErgo one worth pointing out:

- The platform is widened to reach all the way to the edge of the thumb cluster
- The platform is elongated to be taller, and follow the curve that the number row is usually on
- The platform is deepened to go much lower, allowing the most flexibility for the amount of stuff you can put inside (however, this may limit how low you can tent the Glove80, but should accomodate the default height)
- It has a hole and a platform inside for the USB-C connector, and guide rails for the rocker board
- It has a detachable bottom cover to contain and protect the electronics inside

I've taken a liking to using this ABS-like resin, but feel free to use what you like.

# Assembly

Carefully slide
