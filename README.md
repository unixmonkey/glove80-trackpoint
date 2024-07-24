 # Glove80-Trackpoint
Trackpoint sidecar mod for the Glove80 keyboard

![glove80-left-with-trackpoint](https://github.com/user-attachments/assets/d2faad88-5a96-45db-8982-0737be08cd68)

## Why

I recently started getting RSI-like pain and went on a deep dive into the word of ergonomic split keyboards, but I knew part of my issue was my mouse usage habits, and that moving from the keyboard to the mouse (or trackpad) over and over again certainly wasn't helping.

Unfortunately, there currently are very few commercially available ergonomic keyboards that have built-in pointing devices.
However, the [MoErgo Glove80](https://www.moergo.com/collections/glove80-keyboards) keyboard tries to be highly ergonomic, as well as [customizable](https://www.moergo.com/pages/glove80-ergonomic-keyboard-customization) platform, and even provides built-in anchor points and some basic 3d models that can be used to add your own pointing devices right between the thumb cluster and forefinger areas. I figured this could be how I could possibly _make_ the Glove80 the perfect keyboard for me.

So I bought the Glove80, and a 3d printer, and got to work. This is helping me, and so I hope my efforts can help others.

## What you'll need

1. The [MoErgo Glove80 keyboard](https://www.moergo.com/collections/glove80-keyboards)
2. Soldering equipment, [some wire](https://www.amazon.com/gp/product/B01EV70C78/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1), and a steady hand ([this is a great kit for cheap](https://www.amazon.com/gp/product/B07Q2B4ZY9/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&th=1))
3. A hot glue gun (or regular glue/tape could work in a pinch)
4. A 3D printer (or a friend/library/makerspace/business with one)
5. [USB Overdrive](https://www.usboverdrive.com/) or an equivalent software that allows you to invert x and y axis of your mouse (ideally per-device)
6. Trackpoint / Rocker mouse control board (I used [this one](https://www.aliexpress.us/item/3256804502547098.html))
7. 2.5mm screws (for the Glove80 mounting holes). I'm using 8mm deep ones I got in [this kit](https://www.amazon.com/dp/B0BLCFD9HR)
8. A USB-C breakout board (I used [this treedix board](https://treedix.com/products/treedix-4pcs-usb-type-c-breakout-board-serial-basic-breakout-female-connector-type-pcb-converter-board) also available on [Amazon here](https://www.amazon.com/dp/B096M2HQLK), but this is completely optional. I used it because I wanted to be able to "unplug" at the keyboard, instead of at the computer).
9. These [3d model files](/models/)

## Test the trackpoint

![trackpoint](https://github.com/user-attachments/assets/463f927c-a512-4b79-8001-11ee43161e15)

While unlikely, it's entirely possible the trackpoint may be DOA (Dead on Arrival), so plug it in to a computer and make sure it works before we start questioning our sanity if it somehow no longer works after soldering.
This is also a good time to install [USB Overdrive](https://www.usboverdrive.com/) (mac), or equivalent software for your computer. We will be installing the Trackpoint board mostly upside-down, so we will want to invert the X and Y axis.

When plugged in and USB Overdrive installed, go into it's settings, and choose the Trackpoint, which shows up for me as `Mouse VID 0x1018 PID 0x1006, Any Application`.

Then go into "Advanced Settings", and check the boxes next to "Invert X axis" and "Invert Y axis":

![usb-overdrive](https://github.com/user-attachments/assets/2bb68b5e-5e0c-4f5d-8474-0e5304376774)
![overdrive2](https://github.com/user-attachments/assets/8e26b8f9-85ca-4943-9d29-049e2e78bd0c)

Now, the trackpoint should work correctly while upside-down.

## Soldering

The trackpoint rocker board (blue) comes pre-soldered onto the control board (green), but together they are too big (in my opinion) to get the trackpoint in a spot really close enough to comfortably reach, so let's de-solder that, and re-solder the 2 parts together using some wire instead. Be sure to solder on the BACK side of the blue board, or you'll have trouble with the trackpoint being flush when mounted to the case. I made this mistake, as seen in this photo. It still works, but is less flush to the surface:

![trackpoint half-soldered](https://github.com/user-attachments/assets/a12ba8c3-72b7-4700-80ef-d99302c23af2)

These contacts are very close to each other, so be careful your solder and wires doesn't bridge from one solder point to its neighboring ones. If it does, de-solder and try again. Once finished, plug it in and make sure it still works. If it does, I recommend hot-gluing the wires in place (to protect them from bridging and breaking off easily), and testing again.

Assuming that went well, the next step is to add the USB-C connector (if desired). First take a photo of the wires to make sure you know what color goes where. Try to make your cables a little longer than I did. This is so short, I had trouble getting the big green board in a good position.

![usb-c soldering](https://github.com/user-attachments/assets/853847c8-6fb5-4ad3-ba3a-a044ed8be759)

The Trackpoint only uses 4 pins on it's built-in cable, and the Treedix connector has 6. The red wire is power (VBUS), the black wire is ground (GND), the blue wire is Data - (D-), and the green wire is data + (D+). Solder your wires onto the top surface. There are little holes so you can push your wires though before soldering them in place.

Again, I recommend testing things when done to make sure wiggling the trackpoint moves the mouse at this point, and possibly hot-gluing over the connection if it's good.

## 3d printing

This model should serve as a ready-to-print piece for you, however, I've made some design tweaks over the MoErgo one worth pointing out:

- The platform is widened to reach all the way to the edge of the thumb cluster
- The platform is elongated to be taller, and follow the curve that the number row is usually on
- The platform is deepened to go much lower, allowing you to cram the maximum amount of cables/boards/stuff you can put inside (however, this may limit how low you can tent the Glove80, but should accomodate the default height)
- It has a hole and a platform inside for the USB-C connector
- It has a detachable bottom cover to contain and protect the electronics inside

![left hand model](https://github.com/user-attachments/assets/428b3df6-0126-462a-828f-b1354cc94f4d)
![left-hand-back](https://github.com/user-attachments/assets/42dfc230-2bdd-41da-939a-ed0dfaf01674)

If you want to use on the right-hand of the Glove80, mirror the model along the flat outer surface.

Make sure that the USB-C board platform, and bottom screw surfaces are flat and free from support dots. Use the edge of a flathead screwdriver or knife if needed.
Make sure the top and bottom parts fit neatly together. I recommend carefully screwing them together to thread them before putting anything inside.

## Assembly

1. Take the rubber nub off of the rocker board, and position it in the corner like this, and put the rubber nub back on through the hole. This should keep it centered. It won't be perfectly upright, but should be as close as you can get it. I've found a little bit crooked is ok, but a lot feels off, even though it follows the sweep of your thumb, it doesn't match up with the screen, and feels weird.

2. Hot glue the blue rocker board down, leaving a few spots open so, if necessary, you can get under it with a flathead screwdriver to remove later if needed.

![glued-rocker](https://github.com/user-attachments/assets/db1ecd85-080b-4c1c-85d0-3cd586cf8329)

3. Carefully slide the USB-C board into the platform. it should go into the rounded hole first, and be a little difficult to get in there, but once all the way in, it should pop down into the platform. This can be screwed, hot-glued, or taped down.

4. Stuff the rest of the wires in the case. The green board is large, so you'll need to tuck it in under the USB-C platform:

![stuff-components](https://github.com/user-attachments/assets/72d05a20-3094-4bf5-9809-14be467a34c0)

6. Put the bottom on and screw it in

![back-on](https://github.com/user-attachments/assets/6078b19d-477a-41d9-9a05-34b77833fd0c)

8. Connect a USB-c cable from the Trackpoint mouse to your computer, and make sure it still works

## Glove80 mouse-keys configuration

Because the mouse we've just printed doesn't have the mouse buttons wired up, we probably want to map some keys on the Glove80 to act as mouse buttons.
I've setup the 2 right and bottom-most thumb keys to act as mouse buttons in [my layout](https://my.glove80.com/#/layout/user/2e9038ef-1ab4-45dc-9edd-4a34c662d1fc) by assigning them to the "CUSTOM" behavior with `&mkp MB1` for left-click and `&mkp MB2` for right-click (I did not setup middle-click).

![thumb-buttons](https://github.com/user-attachments/assets/51838a18-f06e-4d03-8430-dec2b59a7873)

It is not at all necessary, but you might consider setting up a "mouse" layer like mine above, now that you will be building a firmware capable of emulating a mouse, you might want to take advantage of that.

By default, the MoErgo editor does not build a ZMK firmware with mouse support, so after saving your changes, but before building the firmware, go to "settings" at the top, and change the firmware to "community.pr23.mouse-keys.20240223.113355" or the modern equivalent you see there. One day, ZMK should merge mouse support into main, and this step may not be needed any longer.
![mouse-pr](https://github.com/user-attachments/assets/9fc0f0fd-7894-47cb-8bb1-e3797d4ec1f4)

Once you flash your Glove80 with the new firmware, these keys should act as mouse buttons.

## Result

![glove80-left-with-trackpoint](https://github.com/user-attachments/assets/27213585-940c-4b9b-92a7-232cd66db891)
![on-tray](https://github.com/user-attachments/assets/55c7a682-9e07-4ba5-ba30-455f57071726)

## Bonus

I do most of my computer work on a Mac computer, and also use [Homerow](https://homerow.app) to add some very helpful navigation stuff. `CMD+h` will pepper your active window with a bunch of 2-letter key combos, that when typed will send a left-click at that spot/menu/link, and `CMD+j` makes whatever is focused scrollable. It's _almost_ enough to replace a lot of light mouse usage, and I highly recommend it.

## TODO

- I plan to soon also make the actual Trackpoint buttons work with individual wired keyswitches. I have some Kalih switches and am working on making nice mounting holes for them in the 3d model.
- The height/angle of the top does't _quite_ line up with the Glove80 notch
- My screw mounts could use some work. The screw holes are a little small, and the screws aren't recessed enough to be flush
- I may make it a little thinner on the underside in this specific model, and post a version of the deep model as a generic starter model for _your_ projects

## See Also

- My [Glove80 Wireless Trackball mod](https://github.com/unixmonkey/glove80-trackball) (in progress)
- My [Glove80 Ergo Touchpad mod](https://github.com/unixmonkey/glove80-touchpad) (in progress)

I love the freedom from RSI pain this keyboard has saved me from, and I love it even more with these mouse-replacements. My pain has gotten much more managable, and I've enjoyed getting into 3d modeling and printing!

Thank you to the many people who have posted on the [MoErgo Discord Community](https://www.moergo.com/discord) that helped inspire me to make this happen, and are always dropping great tips on how to optimize my computing experience.
