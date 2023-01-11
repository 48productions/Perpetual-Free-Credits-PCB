# Perpetual Free Credits PCB (a.k.a. the PFC PCB)
This is a simple circuit/PCB design for a a reversible, non-destructive arcade cabinet addon board.


It keeps compatible games fully credited up at all times, perfect for arcade games that either lack a Free Play mode, or are missing features in Free Play mode that are present in Credit mode.

## How it Works

This board connects to the power wires for the Coin Blocker relay on your arcade cabinet. The coin blocker is a relay attached to the game's coin acceptor that will reject any coins (even valid ones) whenever the game is not ready to accept coins (powered off, maximum credit limit reached, etc).

When the game is ready to accept coins, it powers the coin blocker to let coins in. This turns on the PFC board, which will repeatedly trigger the game's coin switch. When the game hits the maximum credit limit, it powers off the coin relay (and thus the PFC board), which stops inserting coins. This way, your game is always credited up and ready to play.

This design is currently a WIP, and is not fully tested. A prototype using similar (but not identical) parts is confirmed to work on a limited set of games.


## Compatibility/Installation

### Compatibility List
The PFC board is known compatible with:
 - To be determined once board design is finalized


### Checking Compatibility
For games not on the list, verify that:

 - Your game has a coin blocker relay on the coin acceptor (common in older games and JP-import games)
 - The game powers the coin blocker relay with anywhere between 10-30VDC (or 5VDC, with modifications to the Perpetual Free Play board).
 - The relay energizes when the game boots up into attract mode.
 - The game has a credit limit, and will turn off the relay when this limit is reached (this is not always the case, especially on some Konami games)!

In modern games, the relay can usually be toggled on/off in the game's test mode (look for an "Output Test" menu).


### To Install:
 - Identify the positive and negative wires that power the coin blocker, using either a multimeter or the game's schematics.
 - Power off the game and disconnect the coin blocker. Connect the coin blocker wires to the power input terminals on the PFC board.
   - Connect positive to the red terminal on the board, negative to white. __Reversing the two may damage the PFC board.__
 - Attach the wires going to the coin switch itself to the coin output terminals on the PFC board.
   - Like the coin blocker, connect negative (usually black) to white, positive to red. Reversing the two shouldn't damage anything, but the board will not function.


### For 5V Coin Blocker Installation:
If your game uses a 5V coin blocker relay, you must bypass the on-board voltage regulator.

1) Cut the "5V Reg Bypass" and "5V Reg Enable" jumpers on the right side of the board with an x-acto knife. Check that the two pads of each jumper have NO continuity with a multimeter.
2) Bridge the bottom two pads of the "5V Reg Bypass" jumper with solder, leaving the top pad disconnected.

With these mods, the PFC board will *only* accept 5V power input. __Higher voltages will damage the board__.
To revert this mod, reverse these steps.


## Troubleshooting

Two LEDs are on the board to assist with troubleshooting.

### Power LED never lights, game does not coin up
Check the power connections to the PFC board.

Ensure the game's coin blocker output is working, and that the voltage it outputs is in the right voltage range for the PFC board.


### Power LED lights and coin LED blinks, but coins do not insert.
Check the coin connections to the PFC board. Try reversing the connections of the two coin wires.

Some games may not accept coins when in test mode, regardless of the coin blocker state.

### PFC board keeps inserting coins even if the game isn't fully in-game/after the credit limit is reached
Check that the PFC board is connected to a coin blocker signal and not wires that are always powered when the game is on (like for a lamp, coin validator power, etc).

Some games may not accept coins when in test mode, regardless of the coin blocker state.

### Power LED on, Coin LED either stays lit or never lights
The PFC board's timing circuit is not working. If adjusting the speed adjustment dial does not fix this, the PFC board must be repaired.

## Components

### Timing Resistors

These values may need to be tweaked during testing.

Off time: R2 (10k + 9k)

Speed: R1 (1k) + VR1 (~4k)


## Credits/Disclaimers

This project came about because of a few relevant conversations in the awesome western arcade rhythm game community, and the general concept/design was discussed by several community members.

You are installing this board at your own risk, and I cannot be held liable for damages, destruction, magic smoke escaping, or otherwise.

For arcade games on an official online network, your network may not allow the use of this board or similar mods. As such, usage of this board in these circumstances isn't recommended.
