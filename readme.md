# Charybdis 3x6 with Dongle and ZMK STUDIO

![3x6](https://github.com/devpew/charybdis-3-6-dongle-prospector-studio/blob/main/img/1.JPG)

## What is a dongle and why is it needed?

A dongle is essentially a third controller. It's the same as the two controllers used in the two halves of the keyboard.

In a typical keyboard, it can work without a dongle. However, in this case, one of the controllers in one half must be the primary controller, and the other must be the secondary controller. In this case, the primary controller maintains two connections: one with the computer the keyboard is connected to, and one with the other half. Because of this, the battery in the primary half drains several times faster.

A dongle prevents this; it is essentially the primary controller, and when used, the controllers in the two halves act as secondary controllers. Because of this, their batteries will hold a charge significantly longer.

The dongle's second advantage is that it can work in the BIOS (before the OS boots and Bluetooth initializes) and can also work with computers that don't have Bluetooth at all.

Dongle Types

For this particular firmware version of the dongle, you can use three controllers:

- nice-nano-v2 and its analogs
- xiao ble
- Prospector (which actually also has a xiao ble controller inside)

| Nice Nano v2 | Xiao | Prospector |
| ------ | ------- |
| ![nicenano](https://github.com/devpew/charybdis-3-6-dongle-prospector-studio/blob/main/img/2.JPG) | ![xiao](https://github.com/devpew/charybdis-3-6-dongle-prospector-studio/blob/main/img/3.JPG) | ![Prospector](https://github.com/devpew/charybdis-3-6-dongle-prospector-studio/blob/main/img/4.JPG) |

## How do I use the mouse? Where are the buttons?

When you start moving the ball, the buttons on the left thumb cluster turn into mouse buttons. Once you stop moving the mouse cursor, they return to normal buttons.
If you don't like this option and would like the mouse buttons to always be present and independent of the ball's movement, you can reconfigure this behavior in the charybdis.keymap file.

![Mouse](https://github.com/devpew/charybdis-3-6-dongle-prospector-studio/blob/main/img/15.JPG)

If you want to adjust the amount of time the buttons remain mouse buttons after the ball moves, you can do so in the Update split_input_common.dtsi file.
This is done in the line `input-processors = <&auto_mouse_layer MOUSE 5000>;`

## How to use ball scrolling?

The keyboard has a rather interesting feature: scrolling content in all directions using the trackball.

In my firmware, the trackball starts scrolling when I hold down the middle button in the left thumb cluster.

In the split_input_common.dtsi file, you can set up inversions for any axis.

## How to use ZMK STUDIO

ZMK STUDIO is a graphical program that lets you change the layout on the fly. You don't have to dig into the code. Changes are applied immediately.

To use it, you need a client.

You can use ZMK STUDIO in your browser via the website https://zmk.studio/, but it's more convenient to download the native client here. It's available for any OS - https://zmk.studio/download

You also need to add `&studio_unlock` to a key or combination in your layout.

If you launch ZMK when your keyboard isn't connected to your computer (or if your keyboard doesn't have ZMK STUDIO support enabled in the firmware), you'll see a blank window.

If you connect a keyboard, you'll see it in ZMK.

After that, you can click on the keyboard you want to connect to (there may be several if you have multiple keyboards connected to your computer; in this case, select the one you need).

![Prospector](https://github.com/devpew/charybdis-3-6-dongle-prospector-studio/blob/main/img/16.png)

ZMK STUDIO will ask you to unlock the keyboard in order to make changes to the firmware. You need to press the button (or combo) where you inserted &studio_unlock.

In my current keyboard layout, this is set to a combo between the first and fifth buttons. Press them simultaneously, and ZMK STUDIO will unlock.

![12323232](https://github.com/devpew/charybdis-3-6-dongle-prospector-studio/blob/main/img/5.JPG)

To unlock, press the buttons as shown in the picture. Press both of these buttons simultaneously.

![12323232](https://github.com/devpew/charybdis-3-6-dongle-prospector-studio/blob/main/img/18.png)

After that, we'll see the ZMK STUDIO interface, where you can change all key assignments on the fly.

![123123](https://github.com/devpew/charybdis-3-6-dongle-prospector-studio/blob/main/img/17.png)

If you don't want to unlock ZMK STUDIO every time, you can add this parameter - CONFIG_ZMK_STUDIO_LOCKING=n

## How to compile the firmware

You can compile the firmware via GitHub or build it locally.

The easiest way is to build it via GitHub. Building locally is more difficult, and you can read guides online on how to do this.
