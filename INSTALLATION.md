# Installation (10V-30V Coin Blocker)
 1) Identify the positive and negative wires that power the coin blocker, using either a multimeter or the game's schematics.
 
 2) Power off the game and disconnect the coin blocker. Connect the coin blocker wires to the power input terminals on the PFC board.
   - Connect positive to the red power terminal on the board, negative to white. __Reversing the two may damage the PFC board.__
 3) Attach the wires going to the coin switch itself to the "Coin Out" terminals on the PFC board.
 
   - Like the coin blocker, connect negative (usually black) to white, positive to red. Reversing the two shouldn't damage anything, but the board will not function.


# Installation (5V Coin Blocker Mod)
If your game uses a 5V coin blocker relay (do these even exist?), you must bypass the on-board voltage regulator.

1) Cut the "5V Reg Bypass" and "5V Reg Enable" jumpers on the right side of the board with an x-acto knife. Check that the two pads of each jumper have NO continuity with a multimeter.

2) Bridge the bottom two pads of the "5V Reg Bypass" jumper with solder, leaving the top pad disconnected.

With these mods, the PFC board will *only* accept 5V power input and can be installed using the above steps. __Higher voltages will damage the PFC Board__.
To revert this mod, reverse these steps.


# Speed Adjustment
Turn the dial between the Power and Coin terminals with a small screwdriver to adjust the rate that the PFC board inserts coins at.

This is mostly up to personal preference, but may help with troubleshooting game-specific compatiblity.