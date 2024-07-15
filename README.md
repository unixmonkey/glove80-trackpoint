# Glove80-Trackpoint
Trackpoint sidecar mod for the Glove80 keyboard

## Why

I recently started getting RSI-like pain and went on a deep dive into the word of ergonomic split keyboards, but I knew part of my issue was my mouse usage habits, and that moving from the keyboard to the mouse (or trackpad) over and over again certainly wasn't helping.

Unfortunately, there currently are very few commercially available ergonomic keyboards that have built-in pointing devices.
However, the [MoErgo Glove80](https://www.moergo.com/collections/glove80-keyboards) keyboard tries to be highly ergonomic, as well as [customizable](https://www.moergo.com/pages/glove80-ergonomic-keyboard-customization) platform, and even provides built-in anchor points and some basic 3d models that can be used to add your own pointing devices right between the thumb cluster and forefinger areas. I figured this could be how I could possibly make the Glove80 the perfect keyboard for me.

So I bought the Glove80, and a 3d printer, and got to work. This is helping me, and so I hope my efforts can help others.

## What you'll need

1. The MoErgo Glove80 keyboard
2. Soldering equipment, some wire, and a steady hand
3. A hot glue gun (or regular glue/tape could work in a pinch)
4. A 3D printer (or a friend/library/makerspace/business with one)
5. [USB Overdrive](https://www.usboverdrive.com/) or an equivalent software that allows you to invert x and y axis of your mouse (ideally per-device)
6. Trackpoint / Rocker mouse control board (I used [this one](https://www.aliexpress.us/item/3256804502547098.html)
7. 2.5mm screws. I'm using 8mm deep ones I got in [this kit](https://www.amazon.com/dp/B0BLCFD9HR)
8. A USB-C breakout board (I used [this treedix board](https://treedix.com/products/treedix-4pcs-usb-type-c-breakout-board-serial-basic-breakout-female-connector-type-pcb-converter-board) also available on [Amazon here](https://www.amazon.com/dp/B096M2HQLK), but this is completely optional. I used it because I wanted to be able to "unplug" at the keyboard, instead of at the computer).
9. These [3d model files](/models/)

## Test the trackpoint

While unlikely, it's entirely possible the trackpoint may be DOA, so plug it in and make sure it works before we start questioning our sanity if it somehow no longer works after soldering.
This is also a good time to install [USB Overdrive](https://www.usboverdrive.com/) (mac), or equivalent software for your computer. We will be installing the Trackpoint board mostly upside-down, so we will want to invert the X and Y axis.

When plugged in and USB Overdrive installed, go into it's settings, and choose the Trackpoint, which shows up for me as `Mouse VID 0x1018 PID 0x1006, Any Application`, then go into "Advanced Settings", and check the boxes next to "Invert X axis" and "Invert Y axis".

Now, the trackpoint should work correctly while upside-down.

## Soldering

The trackpoint rocker board (blue) comes pre-soldered onto the control board (green), but together they are too big (in my opinion) to get the trackpoint in a spot really close enough to comfortably reach, so let's de-solder that, and re-solder the 2 parts together using some wire instead. Be sure to solder on the BACK side of the blue board, or you'll have trouble with the trackpoint being flush when mounted to the case (I made this mistake).

These contacts are very close to each other, so be careful your solder and wires doesn't bridge from one solder point to its neighboring ones. If it does, de-solder and try again. Once finished, plug it in and make sure it still works. If it does, I recommend hot-gluing the wires in place, and testing again.

Assuming that went well, the next step is to add the USB-C connector (if desired). First take a photo of the wires to make sure you know what color goes where. Here's mine if you forgot:

The Trackpoint only uses 4 pins on it's built-in cable, and the Treedix connector has 6. The red wire is power (VBUS), the black wire is ground (GND), the blue wire is Data - (D-), and the green wire is data + (D+). Solder your wires onto the top surface. There are little holes so you can push your wires though before soldering them in place.

Again, I recommend testing things when done to make sure wiggling the trackpoint moves the mouse at this point, and possibly hot-gluing over the connection if it's good.

## 3d printing

This model should serve as a ready-to-print piece for you, however, I've made some design tweaks over the MoErgo one worth pointing out:

- The platform is widened to reach all the way to the edge of the thumb cluster
- The platform is elongated to be taller, and follow the curve that the number row is usually on
- The platform is deepened to go much lower, allowing the most flexibility for the amount of stuff you can put inside (however, this may limit how low you can tent the Glove80, but should accomodate the default height)
- It has a hole and a platform inside for the USB-C connector
- It has a detachable bottom cover to contain and protect the electronics inside

I've taken a liking to using this ABS-like resin, but feel free to use what you like.

Make sure that the USB-c board platform, and bottom screw surfaces are flat and free from support dots. Use the edge of a flathead screwdriver or knife if needed.
Make sure the top and bottom parts fit neatly together. I recommend carefully screwing them together before putting anything inside.

# Assembly

1. Carefully slide the USB-c board into the platform. it should go into the rounded hole first, and be a little difficult to get in there, but once all the way in, it should pop down into the platform. This can be screwed, hot-glued, or taped down.
2. Take the rubber nub off of the rocker board, and position it in the corner like this, and put the rubber nub back on through the hole. This should keep it centered.
3. Hot glue the blue rocker board down, leaving a few spots open so, if necessary, you can get under it with a flathead screwdriver to remove later if needed.
4. Stuff the rest of the wires in the case and put the bottom on
5. Connect a USB-c cable from the Trackpoint mouse to your computer, and make sure it still works

# Glove80 mouse-keys configuration

Because the mouse we've just printed doesn't have the mouse buttons wired up, we probably want to map some keys on the Glove80 to act as mouse buttons.
I've setup the 2 right and bottom-most thumb keys to act as mouse buttons in [my layout](https://my.glove80.com/#/layout/user/2e9038ef-1ab4-45dc-9edd-4a34c662d1fc) by assigning them to the "CUSTOM" behavior with "&mkp MB1" for left-click and "&mkp MB2" for right-click (I did not setup middle-click).

It is not at all necessary, but you might consider setting up a "mouse" layer like mine above, now that you will be building a firmware capable of emulating a mouse, you might want to take advantage of that.

By default, the MoErgo editor does not build a ZMK firmware with mouse support, so after saving your changes, but before building the firmware, go to "settings" at the top, and change the firmware to "community.pr23.mouse-keys.20240223.113355" or the modern equivalent you see there. One day, ZMK should merge mouse support into main, and this step may not be needed any longer.

Once you flash your Glove80 with the new firmware, these keys should act as mouse buttons.

# Bonus

I do most of my computer work on a Mac computer, and also use [Homerow](https://homerow.app) to add some very helpful navigation stuff. `CMD+h` will pepper your active window with a bunch of 2-letter key combos, that when typed will send a left-click at that spot/menu/link, and `CMD+j` makes whatever is focused scrollable. It's _almost_ enough to replace a lot of light mouse usage, and I highly recommend it.

# TODO

I plan to soon also make the buttons work with individual wired keyswitches. I have some Kalih switches and am working on making nice holes for them in the 3d model.
