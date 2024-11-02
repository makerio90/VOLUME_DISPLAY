# VOLUME_DISPLAY
this is a project i have been working on for the better part of a month now, this is only the first commit as i have dicided to add the project to github.

## The Idea:
i wanted to make a volumetric pov display. i got insperation from these projects:

- [this project is what kicked it off](https://hackaday.com/2024/09/09/doom-on-a-volumetric-display/)
- [and this served as insperation](https://hackaday.com/2021/02/21/volumetric-3d-television-is-here/)

both work off of the same principle: phisicly rotating an led matrix to create the sense of volume.

this seemed doable so i started work on schematics.

## theory of operation
cutting to the chase here: this is what the mainboard needs to do:

the main board is intended to drive a 32x16 led matrix at a high framerate (>1000fps).
new frames will be added to a framebuffer through a rs-485 bus. 12v power will also be supplied.
a hall effect sensor will provide a sync signal, allowing the board to make minor ajustments to its framerate.
most importently, this whole board rotates around. 12v and rs485 is fed through a slipring.

the entire board must be slowed to a stop in order for the rp2040 to be programmed.
whenever the usb port is plugged in. the rp2040 will be powered and in prog mode.
*the led drivers should be off when usb is plugged in!*

the board will be in the shape of a circle. the led matrix will be mounted vertically in the center via the attached pinheders.
because the board will likely be unbalanced, nuts and bolts will be added around in a circle to provide an option for balance.

## 4-layer stackup

top: high speed traces
in 1: signal, power & ground
in 2: Ground only
BOT: low speed, high current traces.