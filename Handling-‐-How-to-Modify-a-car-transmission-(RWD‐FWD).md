Yes, it's possible :thumbsup:

The parameter in '**handling.meta**' you need to edit is this:

**100% Front Wheel Drive:**
```xml
      <fDriveBiasFront value="1.000000" />
```
**Four-Wheel Drive (50/50 equal drive to front & rear):** 
```xml
      <fDriveBiasFront value="0.500000" />
```
**100% Rear Wheel Drive:**
```xml
      <fDriveBiasFront value="0.000000" />
```

**4WD DRIVE BIAS OPTIONS:**
You can enter any combination of drive bias you like. 70% Rear, 30% Front would be:
```xml
      <fDriveBiasFront value="0.300000" />
```
For a four-wheel drive car you have a wealth of options as, for example with the 70/30 bias above, you will still visually see drive to the front wheels in-game (even though there is not equal drive given to the front & rear) so there is no need to stick to 50/50 if you want 4WD :thumbsup: Can make for some awesome handling setups :slight_smile: :thumbsup:
 
**Note:** When you change this parameter, say from RWD (0.0000) to 50/50 4WD (0.5000), it will drastically change the handling feel of the car. You will need to re-work the handling again to get the car to feel right so this should be one of the first parameters you edit when creating a car's handling setup :thumbsup:

**Useful Parameters:**
```xml
      <fTractionBiasFront value="0.450000" />
```

This edits the entire grip profile (ie lateral grip as well as drive/forward grip) of the tyres front to rear (100% Front=1.000, 100% Rear=0.000, the same as '**<fDriveBiasFront**' (although '**<fTractionBiasFront**'  usually works best in the range of **~'0.4'>'0.6'**)). 
It's a nice parameter to edit & can fix just about any handling once you have got most of the other parameters set. Mostly it controls how the car feels when drifting/cornering. I usually get close to what I want with other parameters & then start tweaking '**<fDriveBiasFront**' to get a nice balanced power drift dialed in :thumbsup: