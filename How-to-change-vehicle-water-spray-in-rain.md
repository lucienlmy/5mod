Try **vfxvehicleinfo.ymt** 
It can now be opened & extracted using OpenIV (Ctrl+S when file is highlighted in OpenIV or right-click the file & select 'Extract to META/XML (.xml)').

 
There are 2 locations for the file:

\mods\update\update.rpf\x64\data\effects\vfxvehicleinfo.ymt

\mods\x64a.rpf\data\effects\vfxvehicleinfo.ymt

**Note:** You can search for 'vfxvehicleinfo.ymt' in OpenIV using Ctrl+F3 (Also 'Tools' tab> 'Search')

Edit the one in update.rpf (Only edit the one in x64a.rpf if you do NOT have one in update.rpf).


**Note:** When putting the edited file back using OpenIV don't change the '.ymt.xml' file extension just drag & drop it as is & OpenIV will convert it to a .ymt on it's own :thumbsup:

In 'vfxvehicleinfo.ymt' there are various item types. You will be mostly interested in:

<Item type="CVfxVehicleInfo" key="VFXVEHICLEINFO_CAR_GENERIC">

<Item type="CVfxVehicleInfo" key="VFXVEHICLEINFO_CAR_BULLET">

<Item type="CVfxVehicleInfo" key="VFXVEHICLEINFO_CAR_ELECTRIC">

<Item type="CVfxVehicleInfo" key="VFXVEHICLEINFO_CAR_HOTKNIFE">

There are others for forklift, golf car, motorbikes, trains, trucks etc

Under these headings (right at the very bottom of each) are these settings:

      <splashInPtFxEnabled value="true"/>
      <splashInPtFxRange value="100.00000000"/>
      <splashInPtFxName>water_splash_veh_in</splashInPtFxName>
      <splashInPtFxSizeEvoMax value="9.00000000"/>
      <splashInPtFxSpeedDownwardThresh value="2.00000000"/>
      <splashInPtFxSpeedLateralEvoMin value="2.00000000"/>
      <splashInPtFxSpeedLateralEvoMax value="18.00000000"/>
      <splashInPtFxSpeedDownwardEvoMin value="2.50000000"/>
      <splashInPtFxSpeedDownwardEvoMax value="18.00000000"/>
      <splashOutPtFxEnabled value="true"/>
      <splashOutPtFxRange value="50.00000000"/>
      <splashOutPtFxName>water_splash_veh_out</splashOutPtFxName>
      <splashOutPtFxSizeEvoMax value="9.00000000"/>
      <splashOutPtFxSpeedLateralEvoMin value="0.00000000"/>
      <splashOutPtFxSpeedLateralEvoMax value="2.00000000"/>
      <splashOutPtFxSpeedUpwardEvoMin value="0.00000000"/>
      <splashOutPtFxSpeedUpwardEvoMax value="2.00000000"/>
      <splashWadePtFxEnabled value="true"/>
      <splashWadePtFxRange value="50.00000000"/>
      <splashWadePtFxName>water_splash_veh_wade</splashWadePtFxName>
      <splashWadePtFxSizeEvoMax value="9.00000000"/>
      <splashWadePtFxSpeedVehicleEvoMin value="4.00000000"/>
      <splashWadePtFxSpeedVehicleEvoMax value="15.00000000"/>
      <splashWadePtFxSpeedRiverEvoMin value="0.00000000"/>
      <splashWadePtFxSpeedRiverEvoMax value="15.00000000"/>
      <splashTrailPtFxEnabled value="true"/>
      <splashTrailPtFxRange value="50.00000000"/>
      <splashTrailPtFxName>water_splash_veh_trail</splashTrailPtFxName>
      <splashTrailPtFxSizeEvoMax value="9.00000000"/>
      <splashTrailPtFxSpeedEvoMin value="0.50000000"/>
      <splashTrailPtFxSpeedEvoMax value="90.00000000"/>

I haven't edited any of them yet but I'm pretty sure this is what you are looking for. Make a backup of the original file before you start & you will then be free to mess about with the settings to see what each of them do in-game. Best of luck.