# TripleBypassV2Plus
A Variant of Tian Feng's Triple Bypass V2 with fixes and functionality added

## VA3 Installs
Since the VA3 is the target sound profile for the 3BP, it may be desired to simply take the sound output of the on-board audio circuit and use the 3BP to pass it to the 9-pin DIN. These instructions are applicible to ALL variants of the Triple Bypass (V2, V2A, V2+, etc.)
- Do not remove ANY of the audio circuit electrolytic capacitors, as there is no reason to disable any part of the on-board circuit!
-- RGB instructions are unchanged.
- Remove the two output filter capacitors circled below. The reference designators will vary between 3BP versions
-- ![Filter Caps](/images/3BP_RemoveCaps.jpg)
- Solder the "2" jumpers
- Connect pin 8 of the headphone amp to the YR pad and pin 1 to YL
-- ![VA3 Headphone Amp](/images/VA3_HPAmp.jpg)


## Headphone Audio Restoration

### VA3-VA6 (Probably earlier variants as well)
On the bottom of the board under the CXA1034 (or similar) IC, remove:
- C45-C48
- R42-43 (Mono audio amplifier summing resistors)
- R34, 37
- Connect HR to C43-negative and HL to C41-negative

### VA7
- Remove R29-30 and C19-20 (They are next to IC9, lower left hand corner of the board)
- IC9: Lift pins 8 and 14
- On the 3BP V2+
-- Replace R41 and R42 with 10K ohms. Since the install is in a VA7, R24 and R27 will be unused and can be harvested to replace R41 and R42.
- The HR pad will connect to the upper side (facing the AV section) of R46
- The HL pad will connect to the upper side of R45

![VA7 Headphone Amp Connections](/images/Headphone%20Amp%20Connections.jpg)

### For original 3BPV2
While the original 3BPV2 does not have dedicated pads for headphone audio, it is still feasible to implement. 
- Identify the audio output nodes on the 3BP board, which correspond to the audio amp's pins 1 and 7. See the image below for an example using the V2+.
![3BP Audio Output Nodes](/images/3BP_AudioOutputs.jpg)
- Using the applicable instructions above, connect the audio output nodes to the points specified on the main board, through the resistance values indicated below. This can be accomplished with leaded resistors or surface mount resistors.
-- VA3-6: 100K
-- VA7: 10K

## CVBS Restoration

These instructions assume the subcarrier pin has not been lifted!
*** Leave the 3BP S75 jumper open (no solder) for Model 2 ***

-Model 1
For models VA3-VA6 (likely earlier models too, unconfirmed), on the bottom side of the board, remove:
R17/19/21 (4.7 kOhm)

Solder:
RO to the empty pad of R17 that has continuity to C25
GO to the empty pad of R19 that has continuity to C26
BO to the empty pad of R21 that has continuity to C27

-Model 1 VA7, Model 2
Remove R62-64

Solder RO to either pad that junctions R58, C25 and R62
Solder GO to either pad that junctions R59, C26 and R63
Solder RO to either pad that junctions R60, C27 and R64

- Model 3 VA1 *work in progress*
-- Remove R13-15

For Model 2/3 systems, keep Pins 21-23 of the RGB encoder lifted. M1VA7 outputs will be restored to the original DIN and will not impact signals to the 9 Pin DIN.


