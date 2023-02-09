# Perpetual Free Credits PCB (a.k.a. the PFC PCB)
**A Non-Destructive Arcade Game Coinup Mod PCB**


It keeps compatible games fully credited up at all times, perfect for arcade games that either lack a Free Play mode, or are missing features in Free Play mode that are present in Credit mode.

It's designed for games with a **credit limit** that controls a **coin blocker** relay - when the game is accepting credits, this board triggers the coin input until the game hits the credit limit and stops accepting coins. Once you play the game (and thus it is under the credit limit again), another coin is inserted to put the game at the credit limit again.

---
## Compatibility/Installation

Note: This board design is very new and has not been thoroughly tested. Proceed with caution!

### Compatibility List
This board is **compatible** with:
 - ✅ CHUNITHM PARADISE LOST
 - ✅ crossbeats REV. SUNRISE S2

This board is **incompatible** with (as they have no credit limit):
 - ❌ SOUND VOLTEX EXCEED GEAR
 - ❌ jubeat festo


### Checking Compatibility
**For games not on the list, your game MUST:**

 - **Have a coin blocker relay** on the coin acceptor (mostly found in older or JP-import games)
 
 - Power said relay with *10-30VDC* or *5VDC*
 
 - Turn on the relay when the game enters attract mode (you'll hear it click on)
 
 - **Has a credit limit, and will turn off the	Coin Blocker when this limit is reached** (this is not always the case)!

In modern games, the relay can usually be toggled on/off in the game's test mode (look for an "Output Test" menu).


### To Install:
 1) Identify the positive and negative wires that power the coin blocker, using either a multimeter or the game's schematics.
 
 2) Power off the game and disconnect the coin blocker. Connect the coin blocker wires to the power input terminals on the PFC board.
   - Connect positive to the red power terminal on the board, negative to white. __Reversing the two may damage the PFC board.__
 3) Attach the wires going to the coin switch itself to the "Coin Out" terminals on the PFC board.
 
   - Like the coin blocker, connect negative (usually black) to white, positive to red. Reversing the two shouldn't damage anything, but the board will not function.


### For 5V Coin Blocker Installation:
If your game uses a 5V coin blocker relay (do these even exist?), you must bypass the on-board voltage regulator.

1) Cut the "5V Reg Bypass" and "5V Reg Enable" jumpers on the right side of the board with an x-acto knife. Check that the two pads of each jumper have NO continuity with a multimeter.

2) Bridge the bottom two pads of the "5V Reg Bypass" jumper with solder, leaving the top pad disconnected.

With these mods, the PFC board will *only* accept 5V power input. __Higher voltages will damage the PFC Board__.
To revert this mod, reverse these steps.


### Speed Adjustment
Turn the dial between the Power and Coin terminals with a small screwdriver to adjust the rate that the PFC board inserts coins at.

This is mostly up to personal preference, but may help with troubleshooting game-specific compatiblity.


---
## Troubleshooting

Two LEDs are on the board to assist with troubleshooting.

### Power LED never lights, game does not coin up
Check the power connections to the PFC board. Ensure they are not reversed.

Ensure the game's coin blocker output is working (via multimeter or by re-connecting the coin blocker relay), and that the voltage it outputs is in the right voltage range for the PFC board. 5V coin blockers require the modification described above.


### Power LED lights and coin LED blinks, but coins do not insert.
Check the coin connections to the PFC board. Try swapping the two coin wires around.

Some games may not accept coins when in test mode, regardless of the coin blocker state.

### PFC board keeps inserting coins even if the game isn't fully booted/after the credit limit is reached
Check that the PFC board is connected to the coin blocker signal and not to wires that are always receiving power (like for a lamp, coin acceptor power, etc).

Some games continue to accept coins, even when the credit display maxes out "99" coins. These games are incompatible with the Perpetual Free Credits board.

Some games may not accept coins when in test mode, regardless of the coin blocker state.

### Power LED on, Coin LED either stays lit or never lights
The PFC board's timing circuit is not working. If adjusting the speed adjustment dial does not fix this, the PFC board must be repaired.


---
## No Really How Does This Work

This board connects to the power wires for the Coin Blocker relay on your arcade cabinet, if it has one, through voltage regulator U2. Normally, this relay is attached to the game's coin acceptor and will reject any coins (even valid ones) whenever the game is not ready to accept coins (game powered off, maximum credit limit reached, etc).

When the game is ready to accept coins, it powers the coin blocker to let coins in. This turns on the PFC board, which will repeatedly trigger the game's coin switch using timer U1 through opto isolator U3. When the game hits the maximum credit limit, it powers off the coin relay (and thus the PFC board), which stops inserting coins. This way, your game is always credited up and ready to play.

Timing of the pulses is controlled by capacitor C1, resistor R2 (20k, time between pulses), and resistor/potentiometer R1/VR1 (1k + 0-10k, pulse frequency).


---
## Credits/Disclaimers

This project came about because of a few relevant conversations in the awesome western arcade rhythm game community, and the general concept/design was discussed by several community members.

You are installing this board at your own risk, and I cannot be held liable for damages, destruction, magic smoke escaping, or otherwise.

For arcade games on an official online network, your network may not allow the use of this board or similar mods. As such, usage of this board in these circumstances isn't recommended.

*Any games mentioned are properties of their respective owners. This design was produced independently of them, and is in no way endorsed or officially supported.*
