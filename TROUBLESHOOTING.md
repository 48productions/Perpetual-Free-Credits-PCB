# PFC Board Troubleshooting
Two LEDs are on the board to assist with troubleshooting.

## Power LED never lights, game does not coin up
Check the power connections to the PFC board. Ensure they are NOT reversed.

Ensure the game's coin blocker output is working (via multimeter or by re-connecting the coin blocker relay), and that the voltage it outputs is in the right voltage range for the PFC board. 5V coin blockers require the modification described in FABRICATION.md.


## Power LED lights and coin LED blinks, but coins do not insert.
Check the coin connections to the PFC board. Try swapping the two coin wires around.

Some games may not accept coins when in test mode, regardless of the coin blocker state.

## PFC board keeps inserting coins even if the game isn't fully booted/after the credit limit is reached
Check that the PFC board is connected to the coin blocker signal and not to wires that are always receiving power (like for a lamp, coin acceptor power, etc).

Some games continue to power the coin blocker accept coins, even when the credit display maxes out "99" coins. These games are incompatible with the Perpetual Free Credits board.

Some games may power the coin blocker and not accept coins in test mode, keeping the board powered and inserting coins.

## Power LED on, Coin LED either stays lit or never lights
The PFC board's timing circuit is not working. If adjusting the speed adjustment dial does not fix this, the PFC board must be repaired.