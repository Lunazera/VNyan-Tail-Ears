# LZ's Tail & Ears for VNyan

Adds responsive tail and ear movement to your 3D VTuber model! Works through using pendulum chains to control bone rotations.

_note: currently vnyan has a bug that pendulum chains wont save the bone, rotation, or offset values. There are notes in the graph that have the info of what to put here._

Requires at least VNyan version 1.3.4
Ko-fi link: https://ko-fi.com/s/99936effdc
## Tail

![TailGif](https://github.com/Lunazera/VNyan-Tail-Ears/blob/main/images/Tail-Example-animated.gif)

Add dynamic tail movement to your model!
Requires two accompanying pendulum chains, TailSway and TailSwayY.

### Features
- Tail will wag back and forth with controls for speed and amount of movement
- Tail wags faster as you smile, and responds to heartrate
- Head tracking based movement
  - Tail moves opposite to how you look, so it will get out of the way of your direction
  - Tail moves down when you raise your head and when you lean forward (so it wont go into your head)
  - Tail moves along your head tilting

### SETUP
1. Load this graph, and the two pendulum chains.
2. In the chains, set the Avatar GameObject's to be your control bone for your tail. This bone must not have any other animators on it (like springbones)
3. Use the settings reference below to make sure the pendulums are imported correctly. In the Output Values, you'll need to change the Offset and Transform. Make sure the Transforms are Rotation Y and Z for the first chain's outputs, and Rotation X for the second chain output.
4. Change the Offset value for TailSway's first bone output if you want your tail to lean to either the left or right.

### Controls
- TailSpeed = base speed of your tail 
- TailMovement = amount/distance of tail movement
- TailWagAdd = how much smiling increases your tail wagging
- TailMovementReduce = how much heartrate reduces your tail movement (needs Pulsoid)

You can toggle the smile-wagging and heartrate response off and on with these websocket commands: `ToggleTailWag` & `ToggleTailHeartrate`

## Ears
![EarGif](https://github.com/Lunazera/VNyan-Tail-Ears/blob/main/images/Ears-Example-animated.gif)

### Features
- Ears raise up when you raise your eyebrows, and down when you lower them
- Movement is smoothed (no sharp movements!)
- Ears tilt to the side when you tilt your head
- Wiggle when you blink, AND each ear will randomly wiggle over time

### SETUP
1. Load the LeftEar and RightEar pendulum chains
2. Click the search icon for GameObject and find your left ear's control bone. You can use the search menu to try to find it, it'll need to be a bone that doesn't have springbones or dynamic bones applied. For Vroid models, this is usually called something like "CatEar1_01"
3. Use the settings reference below to make sure the pendulums are imported correctly. In the Output Values, you'll need to change the Offset and Transform.

The pendulums will tilt your ears along with your head, raise ears with eyebrow raising, and lower them with your brows down. Also will wiggle if you blink. The graph also includes a little extra thing that will periodically wiggle a random ear :3

# Settings reference
Use these references to make sure the pendulum chain settings are correct

## Tail pendulum settings
### TailSway
Bone = 3, Mult = 7, Offset = 0, Rotation Y

Bone = 3, Mult = 12, Offset = 5, Rotation Z

### TailSwayY
Bone = 3, Mult = 15, Offset = 0, Rotation X

## Ear Pendulum settings
### LeftEar Outputs
Bone = 3, Mult = 6, Offset = -2, Rotation X

Bone = 3, Mult = -5, Offset = 25, Rotation Y

Bone = 3, Mult = 15, Offset = 15, Rotation Z

### RightEar Outputs
Bone = 3, Mult = -6, Offset = -2, Rotation X

Bone = 3, Mult = -5, Offset = -25, Rotation Y

Bone = 3, Mult = 15, Offset = -15, Rotation Z
