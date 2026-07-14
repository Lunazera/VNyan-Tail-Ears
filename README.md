# LZ's Tail & Ears for VNyan
Adds responsive tail and ear movement to your 3D VTuber model! Works through using pendulum chains to control bone rotations.

- Ko-fi link - https://ko-fi.com/s/99936effdc
- VNyan Discord thread - https://discord.com/channels/714814460010823690/1224432257477906552
- *if you use SnekStudio, I also made a basic setup like this for there! - https://git.gay/lunazera/LZTail-SnekStudio*

## Tail Graph
Add dynamic tail movement to your model! Requires two accompanying pendulum chains, TailSway and TailSwayY.

![TailGif](https://github.com/Lunazera/VNyan-Tail-Ears/blob/main/images/Tail-Example-animated.gif)

### SETUP
1. Load this graph, and the two tail pendulum chains. Restart VNyan
2. In the chains, set the Avatar GameObject's to be your control bone for your tail. This bone must not have any other animators on it (like springbones).
   * *if you need to adjust your model to work with this, check the How-To instructions below*
3. Change the Transforms to be the correct rotations for your tail bones movement. TailSway should get your tail's horizontal and twist movement, and TailSwayY should get your tail's vertical movement.
4. Tune controls to the right, and the tail wiggle controls below. If you don't want the extra wiggles, set the setting to 0.
   
#### Controls
- Base Speed = Default wagging speed. Set to 0 if you don't want wagging when idle. 
- Movement Range = Amount or distance of your tail wagging
- Max Speed = Maximum speed your wagging increases to when responsive to your expression
- Acceleration = How fast your tail speeds up to it's max speed
- Deacceleration = How fast your tail slow down back to it's base speed

#### Blendshape Controls
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

#### Cat Mode
Maybe instead of wagging, you just want your tail to change it's position randomly a bit more like a cat's tail. Add this graph to have your tail periodically change positions.


## Ear Wiggles Graph
This is a little extra thing that works with the EarSway Pendulums. It will periodically wiggle a random ear :3 The pendulums will tilt your ears along with your head, raise ears with eyebrow raising, and lower them with your brows down. Also will wiggle if you blink. The graph also includes a little extra thing that will periodically wiggle a random ear :3

![EarGif](https://github.com/Lunazera/VNyan-Tail-Ears/blob/main/images/Ears-Example-animated.gif)

### SETUP
1. Load this graph, and the two ear pendulum chains. Restart VNyan
2. In the chains, set the Avatar GameObject's to be your control bone for your tail. This bone must not have any other animators on it (like springbones). For Vroid models, this is usually called something like "CatEar1_01"
 - note if you need to adjust your model to work with this, check the How To instructions in the tail instructions document.

#### Settings
- Wiggle Min/Max Random Time = Sets the time range between each random ear wiggle
- Wiggle Amount = How long your ear wiggles will last for (in ms)
- Wiggle Speed = How fast the wiggle will move your pendulum. Set smaller to make slower movements

#### Blendshape Controls
- EarLeft - Moves left ear down
- EarRight - Moves right ear down

#### Additional Blendshapes
The pendulums are also already set to respond to your facial expressions. They will move your ears with browouterupleft/right, browdownleft/right, and eyeblinkleft/right
change these in the pendulum chains to map them differently!

# How to set up your Tail/Ear Bones
For this to work, you need at least one bone in your tail that you can use to control it, which <b>cannot have any animator on it.</b> If you are using a VRoid tail for example, this graph won't work and you'll have to make adjustments to your model.
Note: Make sure you're using VRM0, not VRM1

To do this, you will need either Blender or Unity. Below I'll share some instructions for both, but check the GitHub or the VNyan forum thread for more info:
- https://discord.com/channels/714814460010823690/1224432257477906552

### Examples in VNyan forum
- https://discord.com/channels/714814460010823690/1224432257477906552/1228013752880992307
- https://discord.com/channels/714814460010823690/1224432257477906552/1493307590187417721
- https://discord.com/channels/714814460010823690/1224432257477906552/1280460815031599147
- https://discord.com/channels/714814460010823690/1224432257477906552/1256535178671689728

## Blender Instructions:
1. Make sure you have the VRM add-on for blender installed (https://vrm-addon-for-blender.info/en/)
2. Import your model as a VRM
3. Click the VRM tab on the right and open up the springbone section
4. Find the spring bone group that points to your tail (might be called something like FoxTail)
5. Expand the group, and find the dropdown that lists which bone it applies to
6. Change the bone to point to the next one down in the chain (ie FoxTail_02)
7. That's it! Export your model and it should be good!

## Unity Instructions:
1. Make sure you have uniVRM installed for VRM 0.x https://github.com/vrm-c/UniVRM/releases
2. Import your model as a VRM 0.x
3. Find your springbone component on your model that points to your tail (on VRoid's, this is under 'secondary', with the comment 'FoxTail')
4. Open up the Root Bones to see which bone it points to
5. Change the root bone to point to the next one down in the chain (ie FoxTail_02)
6. Export your model as VRM (or as VSFAvatar using the VNyanSDK) and you're done!
