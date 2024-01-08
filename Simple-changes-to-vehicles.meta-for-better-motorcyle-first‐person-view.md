Hello!  As we all know that motorcycle first-person view is weird. As if the camera is sticking on the middle of the fuel tank. And I'd bet it's a pet peeve of everyone who enjoys riding motorycles in GTA V. 
But for some reason this problem doesn't exist on Hakuchou, the camera leans to the side of the bike when turning. So the solution is in it's Vehicles.meta

So here is what I found and I think it's really useful for modders too. Updating to this camera angle to a good motorycle addon or your own favorite ones is icing on the cake. 

Here is a quick terrible quality raw video example of it https://youtu.be/KhlBRa3cSRE

First things first , I'm just a dummie messing with Vehicles.meta so bear that in mind. I may have made unecessary changes too. I just threw stuff together that worked. So if someone knows if there is mistakes, let me know. Use at your own risk and create backups.

- Use OpenIV and open your favorite motorcycles Vehicles.meta 
- Example Bati \Grand Theft Auto V\mods\common.rpf\data\levels\gta5 

1. Change <coverBoundOffsets> to: 

*<coverBoundOffsets>HAKUCHOU2_COVER_OFFSET_INFO</coverBoundOffsets>*

2. ~~Delete  the line	 <POVTuningInfo>~~ Change the line <POVTuningInfo> to:

 *<POVTuningInfo>HAKUCHOU_POV_TUNING</POVTuningInfo>*


3. Change  <bonnetCameraName> to:

*<bonnetCameraName>BIKE_HAKUCHOU_POV_CAMERA</bonnetCameraName>*

4. Change      <povCameraName> to:

 *<povCameraName>BIKE_HAKUCHOU_POV_CAMERA</povCameraName>*

5. 	Change  <firstPersonDrivebyData>

	  *<firstPersonDrivebyData>
        <Item>BIKE_HAKUCHOU_FRONT</Item>*


(6.) You may need to change the offset of the camera especially for other types than sport bikes using the line. 

 *<PovCameraOffset x="0.000000" y="0.000000" z="0.00000" />* 
x=horizontal | y=forward/back | z=up/down


E: 
oggpeg about an hour ago

If this camera angle is used on dirt type bikes like Sanchez there is finally a lean back animation too.
Here is another quick clip demonstration https://youtu.be/8ZdfDyKzqQE