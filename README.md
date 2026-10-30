# TIDAL-KEYS

[![View PCB on KiCanvas](https://hack.club/pcb-badge)](https://kicanvas.org/?repo=https://github.com/ElGOATFilipino/TIDAL-KEYS/blob/main/PCB/Tidal-keys.kicad_pcb)

<p align="center">
  <img src="https://github.com/ElGOATFilipino/TIDAL-KEYS/blob/main/Assets/Tidal_keys_updated.gif" width="100%">
</p>

A 48 button BLE split keyboard with a design based on the geometry dash level "Tidal wave", features 20 sk6803mini-e Leds total, and uses ZMK firmware. It is meant to be used as a regular keyboard, and the distance between each half is up to the user.

I made this because I wanted split keyboard that felt unique to me! And since I love the game "geometry dash", I decided to base the design around one of its most popular community levels: Tidal wave. 

## Features per side:
- 24 white DSA keys
- 10 neopixel SK6803MINI-E LEDs (Light blue underglow)
- BLE
- Hotswap keys
- 1000mAh 1S LiPo battery per side
- Battery sensing

![text](https://github.com/ElGOATFilipino/TIDAL-KEYS/blob/main/Assets/Screenshot%202026-10-28%20192307.png)

## CAD Model: 

Both cases (left and right) are held together using 10 M2 screws and 10 heatset inserts per side. On both halves, 6 screws are used for the pcb and 4 of them for the top part of the case.
The case is made of only three separate pieces: the bottom, the top cover and the battery lid.
**Features of each component:**
- Bottom case: The bottom case has a hole, meant for the battery. This sectionalso has a "tunnel" where the battery cables can easily connect to the PCB battery pads.
- Top lid: The top part features diffrent types decorations from the level "Tidal wave", such as starfish, bubbles and its iconic title screen arrows.
- Battery lid: The battery lid is screwed to the case using 2 self-tapping M2 screws. The PCB sits over the bottom case using a 3x5x3mm spacer at the bottom and a 3x5x2mm spacer at the top per screw; sandwiching the PCB between them to prevent vertical wobble.

![text](https://github.com/ElGOATFilipino/TIDAL-KEYS/blob/main/Assets/Screenshot%202026-10-30%20172440.png)

All case components made using Fusion 360.

## PCB:

Both the schematic and the PCB were designed in Kicad!

**Schematic:**

![text](https://github.com/ElGOATFilipino/TIDAL-KEYS/blob/main/Assets/Screenshot%202026-10-28%20192107.png)


**PCB:** 
Backside of the PCB, since all components that belong to it are meant to be soldered on the back.
I used the regular cherry mx footprints, but its meant to use MX2A. It also has a ground plane! That way there is less wires to connect (plus it looks cleaner)

![text](https://github.com/ElGOATFilipino/TIDAL-KEYS/blob/main/Assets/Screenshot%202026-10-28%20202003.png)


**Wiring diagram (Battery connection):**
This part was made using Canva! 

![text](https://github.com/ElGOATFilipino/TIDAL-KEYS/blob/main/Assets/Screenshot%202026-10-28%20200348.png)


## BOM:
To construct the full split keyboard the following components are required:
- 1 PCB (file includes both halves)
- All six case components (Bottom, top, battery lid for each half)
- 2 Seeed studio XIAO nrf52840 modules
- 20 SK6803MINI-E Leds
- 48 Cherry MX2A switches (prefferably red)
- 48 1N5819 Diodes
- 20 0805 package 100nF capacitors
- 2 0805 package 300-ohm resistors
- 48 Kailh hotswap sockets
- 2 1000mAh 1S LiP Batteries
- 38 1u DSA keycaps (prefferably white)
- 1 1.25u DSA keycap (prefferably white)
- 2 1.75u DSA keycaps (prefferably white)
- 2 2u DSA keycaps (prefferably white)
- 1 2.25u DSA keycap (prefferably white)
- 2 2.75u DSA keycaps (prefferably white)
- 6 2u Clip-in Cherry stabilizers
- 20 16mm Pan head M2 screws (prefferably phillips-style socket)
- 4 4mm self tapping, pan head screws (prefferably phillips-style socket)
- 20 M2 OD3.5 heatset inserts
- 12 3x5x3mm rubber spacers (3mm inner diameter, 5mm outer diameter, 3mm thickness)
- 12 3x5x2mm rubber spacers (3mm inner diameter, 5mm outer diameter, 2mm thickness)

## How to enable BLE support

**Step 1**: Turn on both halves. This is done automatically when connecitng the batteries.

**Step 2:**: Press and hold `LSHIFT` + `G`. This activates a momentary layer that enables diffrent BLE commands.
The following keys assume these functions when the momentary layer is activated:

- `1` → `BT_SEL 1` (Selects bluetooth layer 1)
- `2` → `BT_SEL 2` (Selects bluetooth layer 2)
- `3` → `BT_SEL 3` (Selects bluetooth layer 3)
- `4` → `BT_CLR` (Clears and purges all bluetooth connections)

**Step 3**: Select any of the bluetooth layer 1-3, the left keyboard will automatically connect with the right half, and broadcast a bluetooth pairing request to a host device. The user is free to release all keys after channel selection.

**Step 4**: In the host device's bluetooth tab, pair with "tidal_keys" and estblish a connection with it.

**Step 5:** TIDAL-KEYS is all set and free to use!

## Aditional notes: 

- TIDAL-KEYS does NOT have wired support! It is meant to be 100% BLE.
- Removing the battery to charge it is not necesary, since both keyboard halves contain a USB-C port just for that.
