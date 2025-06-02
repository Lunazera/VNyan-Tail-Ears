# LZ's Tail & Ears for VNyan

Adds responsive tail and ear movement to your 3D VTuber model! Works through using pendulum chains to control bone rotations.

Ko-fi link: https://ko-fi.com/s/99936effdc
## Tail

![TailGif](https://github.com/Lunazera/VNyan-Tail-Ears/blob/main/images/Tail-Example-animated.gif)

Add dynamic tail movement to your model!
Requires two accompanying pendulum chains, TailSway and TailSwayY.

### Features
- Tail will wag back and forth with controls for speed and amount of movement
- Tail wags faster as you smile
- Head tracking based movement
  - Tail moves opposite to how you look, so it will get out of the way of your direction
  - Tail moves down when you raise your head and when you lean forward (so it wont go into your head)
  - Tail moves along your head tilting

### SETUP
1. Load this graph and the pendulum chains.
2. In the chains, set the Avatar GameObject's to be your control bone for your tail. This bone must not have any other animators on it (like springbones)
3. Use the settings reference below to make sure the pendulums are imported correctly. In the Output Values, you'll need to change the Offset and Transform. Make sure the Transforms are Rotation Y and Z for the first chain's outputs, and Rotation X for the second chain output.
4. Change the Offset value for TailSway's first bone output if you want your tail to lean to either the left or right.

### Controls
- Base Speed = Default wagging speed. Set to 0 if you don't want wagging when idle. 
- Movement Range = Amount or distance of your tail wagging
- Max Speed = Maximum speed your wagging increases to when responsive to your expression
- Acceleration = How fast your tail speeds up to it's max speed
- Deacceleration = How fast your tail slow down back to it's base speed

### Blendshape Controls
These are Blendshapes you can use to control your tails position and movement! You could create triggers or websocket buttons to control your tail through these controls, or use them inside your Expressions (ie making your tail lower and stop wagging when sad)
- TailRaise = Moves tail Up
- TailDown = Moves tail Down
- TailLeft = Moves tail to the Left
- TailRight = Moves tail to the Right
- TailMoveMore = Increaes wagging movement range (100 -> doubles)
- TailMoveLess = Decreaes wagging movement range (100 -> 0)
- TailWagMore = Increases base wagging speed (100 -> doubles)
- TailWagLess = Lowers base wagging speed (100 -> 0)
- TailReactOff = Turns off face-reactive wagging

### Cat Mode
Maybe instead of wagging, you just want your tail to change it's position randomly a bit more like a cat's tail. You can call the trigger Cat Mode to have your tail periodically change it's tail position :3

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

### Controls
- Wiggle Min/Max Random Time = Sets the time range between each random ear wiggle
- Wiggle Amount = How long your ear wiggles will last for (in ms)
- Wiggle Speed = How fast the wiggle will move your pendulum. Set smaller to make slower movements

### Blendshape Controls
- EarLeft - Moves left ear down
- EarRight - Moves right ear dow