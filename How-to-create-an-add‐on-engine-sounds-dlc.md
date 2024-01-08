In this tutorial I'm basically supplying a fully functional add-on engines base folder (see '**Add-on Engine Sounds Base Folder DLC**' link just below) with instructions on how to add your own/replace engine sounds into it & create your own tailored add-on engine sound dlc.
Don't let the sprawling monstrosity of this post put you off, it's a pretty easy task once you get the basics down, much easier to do it in person than it is to try & explain it anyway :worried: .  

**For Mod Authors:**
Feel free to rework the pack for your replace sounds & release it, you don't need to ask or nothing, do whatever you want with *anything* that's in it. 
Just change the dlc name, dlc priority & '**<Version value=**' number (see just below) in the '**.rel**' files to avoid conflicts. :thumbsup:

'**<Version value=' (Important if releasing an add-on sound pack):**
All '**.rel**' files contain a '**<Version value=**' line at the top.
The '**<Version value=**' needs to be the same for linked '**.rel**' files (ie files from the same dlc that reference one another), but must be unique to that dlc & *not* the same version number as any other '**.rel**' files in *other* dlc's. Values in the range of 25,000,000 to 90,000,000 seem to be unused by R* & *should* be safe.
Given there are ~65 Million numbers to choose from, it's unlikely two different add-on sound dlc mods would choose the same number, but something to be aware of.


**Requirements:**
-
 

 - [OpenIV](https://openiv.com/)  
Used for access to the game files, exporting '**.awc**' audio containers to openformats (so you can edit the '**.oac**' & '**.wav**' audio files therein) & for reimporting the '**.oac**' & audio files back into the game.
 - [Codewalker](https://discord.com/invite/BxfKHkk) 
Used to export '**.rel**' files to '**.rel.xml**' (so they can be edited) & import them back into the game. 
**Note:** Get an up-to-date version of CodeWalker from that Codewalker Discord link, as the one on the site (v.29) is out of date & unable to export '**.rel**' files to '**.xml**'.

 - [Notepad++](https://notepad-plus-plus.org/downloads/) 
Used to edit exported '**.rel.xml**' files & to create **NUL** spaces in the '**.nametable**' files.
 - [Add-on Engine Sounds Base Folder DLC](https://drive.google.com/file/d/15eQCELIPCfIecUygW8NejqNP7X6WIK7v/view?usp=sharing) 
This is the engine sounds base folder dlc to work from with a couple of modified vigero example engine sounds included already. 

 - '**vigero1**'  - Nice sounding smoother & louder vigero engine with new idle sound.
'**vigero1sc**' - Similar to 'vigero1', but with a supercharger whine added & using a mamba submix to emphasize the supercharger sound.

As soon as the '**addon_engines**' dlc is installed you can use either '**vigero1**' or '**vigero1sc**' in any vehicle's '**vehicles.meta**' '**audioNameHash**' line:

**Example:** 
```xml
      <audioNameHash>vigero1sc</audioNameHash>
```
**Main Files Included in the DLC:**
 - 
 - **dlcaddon_engines_game.dat151.rel**
This is where the engine sound profiles are defined

 - **dlcaddon_engines_sounds.dat54.rel**
This is where the file paths to the audio files the engine sound profiles use are defined
 - **dlcaddon_engines_game.dat151.nametable** & **dlcaddon_engines_sounds.dat54.nametable**
Nametable files are only required if you want the new definitions written in plain English to remain in that form rather than be permanently converted to hash form (hash_12345678 etc) when the game is loaded. ie If you remove the '**.nametable**' files & load the game, the dlc will continue to work perfectly forever, but the next time you export them to XML (using CodeWalker's **RPF Explorer**), the English names will have all been converted to hashes making it harder for you to remember what is what.
The only exception to this is the main engine sound profile names ('**vigero**', '**tampa**' etc), they will remain in English whether you have a '**.nametable**' installed in the dlc or not. Also, English names defined in another '**.nametable**' file in the game ('**mamba_engine_submix_preset**' for example) *don't* need to be entered in your dlc nametables, but you can enter them if you like, it won't do any harm.

**Additional Files:**
The download also includes already exported '**dlcaddon_engines_game.dat151.rel.xml**' & '**dlcaddon_engines_sounds.dat54.rel.xml**' files that are heavily commented with a lot of useful info. Some of which will not be covered in this tutorial due to size constraints, so definitely open them & have a look, they explain a lot about how lines are linked within multiple '**.rel**' files.

**Commenting Your Own Work:**
For those of you who comment your own work. Be aware that comments are removed from the files on importing the '**.rel.xml**' into the game, so always keep a backup.  

**Instructions:**
-

**Exporting the '.rel' files to '.rel.xml'** (so you can edit them with a text editor)**:**
-

 - Install the '**addon_engines**' dlc as per instructions in the Add-on Engine Sounds Base Folder DLC.
 - Test out the '**vigero1**' & '**vigero1sc**' audio name hashes & confirm the '**addon_engines**' dlc is installed correctly & fully functional.
 - Once you've confirmed the dlc is working, quit the game & start Codewalker.
 - In Codewalker select '**[<<]**' (top right) > '**[Tools...]**' > '**RPF Explorer...**'
 - Wait for the '**RPF Explorer**' to load fully (will say '**File cache loaded**' bottom left) & then navigate to:
 - ...\mods\update\x64\dlcpacks\addon_engines\dlc.rpf\x64\audio
 - Now highlight the '**dlcaddon_engines_game.dat151.rel**' & '**dlcaddon_engines_sounds.dat54.rel**' files using **Ctrl+left-click**.
 - Right-click on one of the files & select '**Export XML... Ctrl+S**' & select a folder location to export the files.
 - Find the files you exported & open them with your text editor of choice

**Editing 'dlcaddon_engines_game.dat151.rel.xml'** (where the main audionamehash audio profiles are defined)
-
 - Have a look at the '**dlcaddon_engines_game.dat151.rel.xml**' you exported first & in it you will see that each vehicle engine sound ('**vigero1**' & '**vigero1sc**') has three main sections:

 - **<Item type="Vehicle"**
 - **<Item type="VehicleEngine"**
 - **<Item type="VehicleEngineGranular"** 

a vehicle audio name hash requires all three sections to function correctly.

**Replace Engine Sound to Add-On Engine Sound Example:**
-
 - If for example, you have a replace sound that replaces the '**mamba.awc**' that you want to add into the '**addon_engines**' dlc as an add-on. You would use Codewalker's '**RPF Explorer**' to track to the dlc that contains the '**mamba.awc**' (in this case '**mpapartment**').

**Note:**
You can use either **Ctrl+F3** Searchbox in [OpenIV](https://openiv.com/) or Codewalker's **RPF Explorer**'s search box (top right of window just right of the '**[:shield: Edit mode]**' button) to search for files by name & see their folder structure location.
 - Once you find the correct dlc, track to the '**dlc.rpf\x64\audio\config**' folder structure within that dlc:

**Example** (mpapartment)**:**
...\mods\update\x64\dlcpacks\mpapartment\dlc.rpf\x64\audio\config

 - In that folder you will see some '**.dat**', '**.rel**' & '**.nametable**' files.
 - Using Codewalker's **RPF Explorer**'s  '**Export XML...**' (in it's right-click menu) export the *highest* numbered '**_game.dat###.rel**' & '**_sounds.dat##.rel**' files ('**dlcapartment_game.dat151.rel**' & '**dlcapartment_sounds.dat54.rel**' for example) & open them with your text editor.
 - In the file ending '**_game.dat151.rel.xml**' (in this case '**dlcapartment_game.dat151.rel.xml**') search (**Ctrl+F**) for '**<Name>mamba</Name>**' etc & track to that location.
 - There should only be one result & it should look like this:
```xml
  <Item type="Vehicle" ntOffset="7260">
   <Name>mamba</Name>
   <Unk00 value="0x91004A69" />
```
 - From there track down to find the mamba's '**<Item type="VehicleEngine"**' & **<Item type="VehicleEngineGranular"**  sections also.
 - Together, they all look like this:
```xml
  <Item type="Vehicle" ntOffset="7260">
   <Name>mamba</Name>
   <Unk00 value="0x91004A69" />
   <Engine>mamba_engine</Engine>
   <EngineGranular>mamba_granular_engine</EngineGranular>
   <Horns>hash_A4ACD2B1</Horns>
   <DoorOpen>hash_3AF70609</DoorOpen>
   <DoorClose>hash_DD1A489A</DoorClose>
   <TrunkOpen>hash_5D5CD901</TrunkOpen>
   <TrunkClose>hash_0C1B043A</TrunkClose>
   <Unk08>null_sound</Unk08>
   <Unk09 value="0.5" />
   <SuspensionUp>hash_7CEDC837</SuspensionUp>
   <SuspensionDown>hash_4AEF38F3</SuspensionDown>
   <Unk12 value="0.4" />
   <Unk13 value="1" />
   <Unk14>hash_00C2FB47</Unk14>
   <Unk15 value="0" />
   <Unk16 value="0" />
   <Unk17 value="0" />
   <ScannerParams>mamba_scanner_params</ScannerParams>
   <JumpLandIntact>hash_A5EB71C0</JumpLandIntact>
   <JumpLandLoose>hash_1AF1FCAC</JumpLandLoose>
   <Unk21 value="31" />
   <Unk22 value="36" />
   <RadioFlags value="0x06010000" />
   <IndicatorOn>null_sound</IndicatorOn>
   <IndicatorOff>null_sound</IndicatorOff>
   <Handbrake>hash_F2B35109</Handbrake>
   <Unk27 value="0x00010001" />
   <Unk28>hash_674E1F4D</Unk28>
   <Unk29 value="0x55FC0070" />
   <Unk30>hash_795E90E6</Unk30>
   <Unk31>hash_795E90E6</Unk31>
   <Unk32>hash_2FF627AC</Unk32>
   <StartupSequence>null_sound</StartupSequence>
   <Unk34>null_sound</Unk34>
   <Unk35>hash_F52E6D86</Unk35>
   <Unk36>hash_F52E6D86</Unk36>
   <Unk37 value="6" />
   <Unk38 value="3" />
   <Unk39 />
   <Unk40 value="0" />
   <Sirens />
   <Unk42 value="0" />
   <Unk43 value="0" />
   <Unk44 value="0" />
   <Unk45>hash_0C3F6AD5</Unk45>
   <Unk46>hash_359E05CB</Unk46>
   <Unk47 />
   <TurretSounds />
   <Unk49 value="8" />
   <Unk50 />
   <Unk51 />
   <Unk52 value="0" />
   <ElectricEngine />
   <Unk54 value="0" />
   <ReverseWarning>null_sound</ReverseWarning>
   <Unk56 value="3" />
   <VehicleMaster>null_sound</VehicleMaster>
   <ShutdownBeep>null_sound</ShutdownBeep>
   <Unk59 value="1" />
   <Unk60 value="0" />
   <Unk61 value="1" />
   <Unk62 value="0" />
   <Unk63>null_sound</Unk63>
   <Unk64 value="0" />
   <Unk65 value="0" />
   <Unk66 value="0" />
   <Unk67 />
   <Unk68>null_sound</Unk68>
   <Unk69 />
   <Unk70 value="0" />
   <Unk71>null_sound</Unk71>
   <Unk72>null_sound</Unk72>
  </Item>

  <Item type="VehicleEngine" ntOffset="7266">
   <Name>mamba_engine</Name>
   <Unk00 value="-700" />
   <Unk01 value="0" />
   <Unk02 value="800" />
   <Unk03 value="1600" />
   <EngineLow>hash_00D0A5BA</EngineLow>
   <EngineHigh>hash_1D19CCAE</EngineHigh>
   <ExhaustLow>hash_0E4C254B</ExhaustLow>
   <ExhaustHigh>hash_330B3159</ExhaustHigh>
   <RevsOff>hash_F2671EE2</RevsOff>
   <Unk09 value="-1200" />
   <Unk10 value="1400" />
   <EngineIdleLoop>hash_4685572C</EngineIdleLoop>
   <ExhaustIdleLoop>hash_5ABCA177</ExhaustIdleLoop>
   <Unk13 value="-800" />
   <Unk14 value="2000" />
   <AirIntake />
   <Unk16 value="-800" />
   <Unk17 value="0" />
   <Turbo>null_sound</Turbo>
   <Unk19 value="-600" />
   <Unk20 value="600" />
   <DumpValve>null_sound</DumpValve>
   <Unk22 value="100" />
   <Unk23 value="70" />
   <Transmission>hash_699D9F91</Transmission>
   <Unk25 value="0" />
   <Unk26 value="2400" />
   <Unk27 value="1200" />
   <Ignition>hash_26DE38C2</Ignition>
   <ShutDown>mamba_shutdown_master</ShutDown>
   <Unk30>null_sound</Unk30>
   <ExhaustPops />
   <Unk32>hash_46A99015</Unk32>
   <Unk33 value="0" />
   <FansVolume value="0" />
   <StartupMaster>mamba_startup_master</StartupMaster>
   <Unk36 />
   <Unk37 />
   <Unk38 />
   <Unk39 />
   <Unk40>hash_490413A6</Unk40>
   <Unk41>hash_58337F32</Unk41>
   <Unk42 value="700" />
   <Unk43>hash_AB78E2E9</Unk43>
   <Unk44>hash_79AC0C09</Unk44>
   <Unk45 value="0" />
   <Unk46 value="0" />
   <Unk47 value="0" />
   <Unk48 value="0" />
   <Unk49 value="0" />
   <Unk50 value="0" />
   <DumpValveUpgraded>mamba_dump_valve_master</DumpValveUpgraded>
   <Unk52 value="700" />
   <TransmissionUpgraded>null_sound</TransmissionUpgraded>
   <TurboUpgraded>mamba_veh_turbo</TurboUpgraded>
   <AirIntakeUpgraded>hash_4CF1C005</AirIntakeUpgraded>
   <ExhaustPopsUpgraded>mamba_exhaust_pop_master</ExhaustPopsUpgraded>
  </Item>

  <Item type="VehicleEngineGranular" ntOffset="7279">
   <Name>mamba_granular_engine</Name>
   <Unk00 value="0xAAAAA955" />
   <MasterVolume value="-300" />
   <EngineAccel>mamba_engine_accel</EngineAccel>
   <ExhaustAccel>mamba_exhaust_accel</ExhaustAccel>
   <Unk04 value="0" />
   <Unk05 value="0" />
   <Unk06 value="0" />
   <Unk07 value="0" />
   <Unk08 value="0" />
   <Unk09 value="0" />
   <Unk10 value="0" />
   <Unk11 value="0" />
   <Unk12 value="0" />
   <Unk13 value="100" />
   <Unk14 value="300" />
   <Unk15 value="0" />
   <Unk16 value="0" />
   <Unk17 value="100" />
   <Unk18 value="100" />
   <Unk19 value="0" />
   <Unk20 value="200" />
   <Unk21 value="20" />
   <Unk22 value="0.2" />
   <Unk23 value="0.26" />
   <Unk24 value="0.2" />
   <Unk25 value="0.1" />
   <Unk26 value="0.1" />
   <Unk27 value="0" />
   <Unk28 value="0.2" />
   <Unk29 value="0" />
   <Unk30 value="0" />
   <EngineSubmix>mamba_engine_submix</EngineSubmix>
   <EngineSubmixPreset>mamba_engine_submix_preset</EngineSubmixPreset>
   <ExhaustSubmix>mamba_exhaust_transients_and_eq</ExhaustSubmix>
   <ExhaustSubmixPreset>mamba_exhaust_transients_and_eq_preset</ExhaustSubmixPreset>
   <EngineAccelNPC>mamba_engine_accel_npc</EngineAccelNPC>
   <ExhaustAccelNPC>mamba_exhaust_accel</ExhaustAccelNPC>
   <Unk37>mamba_exhaust_pop_master</Unk37>
   <Unk38 value="0" />
   <Unk39 value="0" />
   <Unk40>hash_490413A6</Unk40>
   <Unk41>hash_58337F32</Unk41>
   <Unk42 value="600" />
   <Unk43 value="4" />
   <Unk44 value="2" />
   <IdleSub>mamba_veh_idle_sub</IdleSub>
   <Unk46 value="0" />
   <Unk47 value="0" />
   <Unk48 value="0" />
   <Unk49 value="0" />
   <Unk50 value="0" />
   <Unk51 value="0" />
   <Unk52>hash_B3BAE87C</Unk52>
   <Unk53>mamba_exhaust_pop_master</Unk53>
   <Unk54 value="0" />
   <Unk55 value="600" />
   <Unk56 value="500" />
   <Unk57 value="500" />
   <Unk58 value="1" />
   <Unk59 value="0.2" />
  </Item>
```
**Note:**
If you have any trouble identifying the three linked sections for a vehicle sound profile (some are in hash form rather than English) refer to [this post here](https://forums.gta5-mods.com/topic/31088/tutorial-how-to-find-the-engine-sound-awc-file-for-any-vehicle/2) for more info on exactly how sections are linked (**hint:** it's the names/hashes, *not* the location in the files, they don't have to be next to each other, although usually they are).  

 - Next you would highlight the three linked sections for a vehicle & copy & paste them into the bottom of the '**addon_engines**' '**dlcaddon_engines_game.dat151.rel.xml**' file here:

**Example** (very bottom of '**dlcaddon_engines_game.dat151.rel.xml**')**:**
```xml
   <Unk57 value="500" />
   <Unk58 value="1" />
   <Unk59 value="0.2" />
  </Item>
  <!-- Paste all three 'Vehicle', 'VehicleEngine' & 'VehicleEngineGranular' sections in here -->
 </Items>
</Dat151>
``` 
 - Once you've done that, track up to the ''**<Name>mamba</Name>**'' etc line & rename it to whatever you want to call your new add-on engine sound.

**Example** ('**mamba**' renamed to '**v8supercharger**')**:**
```xml
  <Item type="Vehicle" ntOffset="7260">
   <Name>v8supercharger</Name>
   <Unk00 value="0x91004A69" />
```
Now find these lines throughout the three vanilla vehicle sound sections you just copied over:
```xml
  <Item type="Vehicle" ntOffset="7260">
   <Name>v8supercharger</Name>

   <Engine>mamba_engine</Engine>
   <EngineGranular>mamba_granular_engine</EngineGranular>


  <Item type="VehicleEngine" ntOffset="7266">
   <Name>mamba_engine</Name>


  <Item type="VehicleEngineGranular" ntOffset="7279">
   <Name>mamba_granular_engine</Name>

   <EngineAccel>mamba_engine_accel</EngineAccel>
   <ExhaustAccel>mamba_exhaust_accel</ExhaustAccel>

   <EngineAccelNPC>mamba_engine_accel_npc</EngineAccelNPC>
   <ExhaustAccelNPC>mamba_exhaust_accel</ExhaustAccelNPC>
  </Item>
```
& rename them all to something like this ('**v8supercharger**' rename example)**:**
```xml
  <Item type="Vehicle" ntOffset="7260">
   <Name>v8supercharger</Name>

   <Engine>v8supercharger_engine</Engine>
   <EngineGranular>v8supercharger_granular_engine</EngineGranular>


  <Item type="VehicleEngine" ntOffset="7266">
   <Name>v8supercharger_engine</Name>


  <Item type="VehicleEngineGranular" ntOffset="7279">
   <Name>v8supercharger_granular_engine</Name>

   <EngineAccel>v8supercharger_engine_accel</EngineAccel>
   <ExhaustAccel>v8supercharger_exhaust_accel</ExhaustAccel>

   <EngineAccelNPC>v8supercharger_engine_accel_npc</EngineAccelNPC>
   <ExhaustAccelNPC>v8supercharger_exhaust_accel</ExhaustAccelNPC>
  </Item>
```

**Renaming the replace '.awc' correctly** (so it functions in-game without the sound being weird/airy)**:**
-
This '**.awc**' part can be completed at *any* point, if you fancy a break from editing '**.rel**' files you can do it now before returning to edit the '**_sounds.dat54.rel.xml**' file, or if you would rather press on & finish all '**.rel.xml**' editing, skip down a section here to '**Editing 'dlcaddon_engines_sounds.dat54.rel.xml'**' & return to this '**.awc**' renaming part at a later date.

 - Find your mamba etc replace '**.awc**' 
 - Using OpenIV, throw it into the game somewhere (a random folder will do) & then right-click it & select '**Export to openformats (.oac)**' (you can delete that replace '**mamba.awc**' from within OpenIV after you've done that. *Don't* delete the original vanilla one tho)
 - Track to the location you exported the '**mamba**' folder & '**mamba.oac**' & rename the folder & '**.oac**' to the name of the new audio hash you put in the '**<Name>mamba</Name>**' line above (in this case '**v8supercharger**')
 - Now, open the '**.oac**' with your text editor of choice & use the '**Replace**' functionality ('**Ctrl+H**' in [Notepad++](https://notepad-plus-plus.org/downloads/)) to replace all the references to '**mamba**' with your new audio hash name ('**v8supercharger**' etc)
 - After that save the ''**v8supercharger.oac**' etc & drag & drop it into the '**addon_engines**' dlc in this location (next to the '**vigero1/vigero1sc.awc**'s):

...\mods\update\x64\dlcpacks\addon_engines\dlc.rpf\x64\audio\sfx\dlc_addon_engines

**Note:**
If the replace sound contains a '**mamba_npc.awc**' (most don't) you would use the same renaming/replacing strategy (highlighted in the last 5 steps) to rename the exported '**.oac**' & folder, replace the references to '**mamba_npc**' etc inside the '**.oac**' with '**v8supercharger_npc**' etc & import it into the same location in OpenIV using drag & drop.

**Editing 'dlcaddon_engines_sounds.dat54.rel.xml'** (where the links to the audio files the audioNamehash profile uses are defined)**:**
-

Ignoring the '**<Version value**' line, the first thing you will see in your exported '**dlcaddon_engines_sounds.dat54.rel.xml**' file is the '**<NameTable>**' section:
```xml
 <NameTable>
  <Item>DLC_ADDON_ENGINES\VIGERO1</Item> 
  <Item>DLC_ADDON_ENGINES\VIGERO1_NPC</Item>
  <Item>DLC_ADDON_ENGINES\VIGERO1SC</Item>
  <Item>DLC_ADDON_ENGINES\VIGERO1SC_NPC</Item>
  <Item>0</Item>
 </NameTable>
```
Links to all the '**.awc**'s you include in the dlc need to be put here. 
So if we added '**v8supercharger.awc**' & '**v8supercharger_npc.awc**' in previous steps we would edit the nametable to look like this:
```xml
 <NameTable>
  <Item>DLC_ADDON_ENGINES\VIGERO1</Item> 
  <Item>DLC_ADDON_ENGINES\VIGERO1_NPC</Item>
  <Item>DLC_ADDON_ENGINES\VIGERO1SC</Item>
  <Item>DLC_ADDON_ENGINES\VIGERO1SC_NPC</Item>
  <Item>0</Item>
  <Item>DLC_ADDON_ENGINES\V8SUPERCHARGER</Item>
  <Item>DLC_ADDON_ENGINES\V8SUPERCHARGER_NPC</Item>
 </NameTable>
```
Under the nametable section in the '**dlcaddon_engines_sounds.dat54.rel.xml**' file there are three main sections that relate directly to a vehicle's engine sound. There is an '**EnvironmentSound**' section & two '**GranularSound**' sections (one for the player vehicle & one for '**_npc**' vehicles).

**Note:**
Ignore the '**SimpleSound**' sections for now, this tutorial is long enough already :worried:
In this case they are the sections that define where the '**vigero1**' & '**vigero1sc**' engine sound profiles get their '**start_up**' ('**hash_9D64B840**') & '**shut_down**' ('**hash_3B393DEA**') sounds from & work on the same principle as the main engine sections. Once you get the basics of what's required, it'll be pretty simple to figure out how **SimpleSound/WrapperSound/RandomizedSound** etc sections work also :thumbsup: 
If after copying the three vanilla sections (**Vehicle**, **VehicleEngine** & **VehicleEngineGranular** ) over to '**dlcaddon_engines_game.dat151.rel.xml**' you leave the '**<ShutDown>**' & '**<StartupMaster>**' lines untouched, your add-on sound will use the default '**start_up**' & '**shut_down** sounds defined for that vehicle, which will work perfectly fine for now at least.

Once you have familiarised yourself with the layout of the '**dlcaddon_engines_sounds.dat54.rel.xml**' file, export the '**_sounds.dat54.rel**' file from the dlc of the replace sound you have ('**dlcapartment_sounds.dat54.rel**' for the '**mamba**' in this case)
Moving to the ***vanilla*** dlc '**_game.dat151.rel.xml**' file briefly ('**dlcapartment_game.dat151.rel.xml**' in the case of the '**mamba**') & using these lines as a guide
```xml
  <Item type="VehicleEngineGranular" ntOffset="7279">

   <EngineAccel>mamba_engine_accel</EngineAccel>
   <ExhaustAccel>mamba_exhaust_accel</ExhaustAccel>

   <EngineAccelNPC>mamba_engine_accel_npc</EngineAccelNPC>
   <ExhaustAccelNPC>mamba_exhaust_accel</ExhaustAccelNPC>
  </Item>
```
 find the three sections in the vanilla dlc '**_sounds.dat54.rel.xml** file that your replace vehicle sound comes from ('**dlcapartment_sounds.dat54.rel.xml**').

Basically, copy whatever is in the '**EngineAccel**', '**ExhaustAccel**', '**EngineAccelNPC**' & '**ExhaustAccelNPC**' lines of the **_game.dat151.rel.xml**' file ('**mamba_engine_accel_npc**' for example) & then move to & search the '**_sounds.dat54.rel.xml**' file for them whether they be in English or in hash ('**hash_12345678**' etc) form.
 
**Example link:** 

'**dlcapartment_game.dat151.rel.xml**' 
```xml
   <EngineAccel>mamba_engine_accel</EngineAccel> 
```
**links to:**

'**dlcapartment_sounds.dat54.rel.xml**'
```xml
  <Item type="GranularSound">
   <Name>mamba_engine_accel</Name>
```

Once identified, copy the 2x '**GranularSound**' & 1x '**EnvironmentSound**' sections over into the '**dlcaddon_engines_sounds.dat54.rel.xml**' file.
After that, edit the '**<Name>**', '**<TrackName>**' & '**<ContainerName>**' lines to match that of the '**addon_engines**' dlc name ('**dlc_addon_engines**') & your chosen **audio hash name/'.awc'** name ('**v8supercharger**' etc).

**Partial Example** (just to illustrate the process)**:** 

**Change this** ('**dlc_apartment**'/'**mamba**')**:**
```xml
  <Item type="EnvironmentSound">
   <Name>mamba_exhaust_accel</Name>
   <Header>
    <Flags value="0x00008000" />
    <Category>hash_F7C35252</Category>
   </Header>
   <UnkByte value="1" />
  </Item>
  <Item type="GranularSound">
   <Name>mamba_engine_accel_npc</Name>
   <Header>
    <Flags value="0x00008001" />
    <Flags2 value="0x9555AAAA" />
    <Category>hash_F7C35252</Category>
   </Header>
   <WaveSlotIndex value="0" />
   <Wave1>
    <ContainerName>dlc_apartment/mamba_npc</ContainerName>
    <FileName>engine_accel</FileName>
   </Wave1>
   <Wave2>
    <ContainerName>dlc_apartment/mamba_npc</ContainerName>
    <FileName>exhaust_accel</FileName>
   </Wave2>
   <Wave3>
    <ContainerName>0</ContainerName>
    <FileName />
   </Wave3>
   <Wave4>
    <ContainerName>0</ContainerName>
    <FileName />
   </Wave4>
   <Wave5>
    <ContainerName>dlc_apartment/mamba_npc</ContainerName>
    <FileName>engine_idle</FileName>
   </Wave5>
   <Wave6>
    <ContainerName>dlc_apartment/mamba_npc</ContainerName>
    <FileName>exhaust_idle</FileName>
   </Wave6>
   <DataItem1>
    <UnkFlags0 value="0" />
    <UnkFlags1 value="0" />
    <UnkByte0 value="0" />
    <UnkByte1 value="0" />
    <UnkFloat value="0.5" />
   </DataItem1>
   <DataItem2>
    <UnkFlags0 value="1" />
    <UnkFlags1 value="0" />
    <UnkByte0 value="0" />
    <UnkByte1 value="0" />
    <UnkFloat value="0.5" />
   </DataItem2>
   <DataItem3>
    <UnkFlags0 value="0" />
    <UnkFlags1 value="0" />
    <UnkByte0 value="0" />
    <UnkByte1 value="1" />
    <UnkFloat value="1" />
   </DataItem3>
   <DataItem4>
    <UnkFlags0 value="1" />
    <UnkFlags1 value="0" />
    <UnkByte0 value="0" />
    <UnkByte1 value="1" />
    <UnkFloat value="1" />
   </DataItem4>
   <DataItem5>
    <UnkFlags0 value="0" />
    <UnkFlags1 value="1" />
    <UnkByte0 value="0" />
    <UnkByte1 value="0" />
    <UnkFloat value="1" />
   </DataItem5>
   <DataItem6>
    <UnkFlags0 value="1" />
    <UnkFlags1 value="1" />
    <UnkByte0 value="0" />
    <UnkByte1 value="0" />
    <UnkFloat value="1" />
   </DataItem6>
   <UnkFloat0 value="0.01" />
   <UnkFloat1 value="0.05" />
   <UnkShort0 value="0" />
   <UnkShort1 value="0" />
   <UnkShort2 value="0" />
   <UnkShort3 value="0" />
   <UnkShort4 value="-600" />
   <UnkShort5 value="0" />
   <TrackName>mamba_engine_accel</TrackName>
   <UnkVecData>
    13.5, 49
    13, 13
   </UnkVecData>
  </Item>
```
**to this** ('**dlc_addon_engines**'/'**v8supercharger**')**:**
```xml
  <Item type="EnvironmentSound">
   <Name>v8supercharger_exhaust_accel</Name>
   <Header>
    <Flags value="0x00008000" />
    <Category>hash_F7C35252</Category>
   </Header>
   <UnkByte value="1" />
  </Item>
  <Item type="GranularSound">
   <Name>v8supercharger_engine_accel_npc</Name>
   <Header>
    <Flags value="0x00008001" />
    <Flags2 value="0x9555AAAA" />
    <Category>hash_F7C35252</Category>
   </Header>
   <WaveSlotIndex value="0" />
   <Wave1>
    <ContainerName>dlc_addon_engines/v8supercharger_npc</ContainerName>
    <FileName>engine_accel</FileName>
   </Wave1>
   <Wave2>
    <ContainerName>dlc_addon_engines/v8supercharger_npc</ContainerName>
    <FileName>exhaust_accel</FileName>
   </Wave2>
   <Wave3>
    <ContainerName>0</ContainerName>
    <FileName />
   </Wave3>
   <Wave4>
    <ContainerName>0</ContainerName>
    <FileName />
   </Wave4>
   <Wave5>
    <ContainerName>dlc_addon_engines/v8supercharger_npc</ContainerName>
    <FileName>engine_idle</FileName>
   </Wave5>
   <Wave6>
    <ContainerName>dlc_addon_engines/v8supercharger_npc</ContainerName>
    <FileName>exhaust_idle</FileName>
   </Wave6>
   <DataItem1>
    <UnkFlags0 value="0" />
    <UnkFlags1 value="0" />
    <UnkByte0 value="0" />
    <UnkByte1 value="0" />
    <UnkFloat value="0.5" />
   </DataItem1>
   <DataItem2>
    <UnkFlags0 value="1" />
    <UnkFlags1 value="0" />
    <UnkByte0 value="0" />
    <UnkByte1 value="0" />
    <UnkFloat value="0.5" />
   </DataItem2>
   <DataItem3>
    <UnkFlags0 value="0" />
    <UnkFlags1 value="0" />
    <UnkByte0 value="0" />
    <UnkByte1 value="1" />
    <UnkFloat value="1" />
   </DataItem3>
   <DataItem4>
    <UnkFlags0 value="1" />
    <UnkFlags1 value="0" />
    <UnkByte0 value="0" />
    <UnkByte1 value="1" />
    <UnkFloat value="1" />
   </DataItem4>
   <DataItem5>
    <UnkFlags0 value="0" />
    <UnkFlags1 value="1" />
    <UnkByte0 value="0" />
    <UnkByte1 value="0" />
    <UnkFloat value="1" />
   </DataItem5>
   <DataItem6>
    <UnkFlags0 value="1" />
    <UnkFlags1 value="1" />
    <UnkByte0 value="0" />
    <UnkByte1 value="0" />
    <UnkFloat value="1" />
   </DataItem6>
   <UnkFloat0 value="0.01" />
   <UnkFloat1 value="0.05" />
   <UnkShort0 value="0" />
   <UnkShort1 value="0" />
   <UnkShort2 value="0" />
   <UnkShort3 value="0" />
   <UnkShort4 value="-600" />
   <UnkShort5 value="0" />
   <TrackName>v8supercharger_engine_accel</TrackName>
   <UnkVecData>
    13.5, 49
    13, 13
   </UnkVecData>
  </Item>
```
Once you have completed that renaming process, jump between the two '**addon_engines**' '**.rel**' files & double-check all the links between them match up:

 '**_game.dat151.rel**'    >>>     '**_sounds.dat54.rel**'

**<EngineAccel>** >>> Player (non-NPC) '**GranularSound**' section & NPC '**<TrackName>**' line
**<ExhaustAccel>** >>> '**EnvironmentSound**' section (same as '<ExhaustAccelNPC>')
**<EngineAccelNPC>** >>> NPC '**GranularSound**' section
**<ExhaustAccelNPC>** >>> '**EnvironmentSound**' section (same as '<ExhaustAccel>')

Once complete, that's the '**.rel**' files finished & all you need to do now (if you want any English names to remain that way for the next export to XML) is add any new English name definitions you added to the '**.nametable**' files.
Well done for getting this far, that's the harder parts over with :slight_smile: :thumbsup:. I now have stumps for fingers :neutral_face:  

**Adding English Names to the '.nametable' Files:**
 -
Grab both the '**.nametable**' files ('**dlcaddon_engines_game.dat151.nametable**' & '**dlcaddon_engines_sounds.dat54.nametable**') from here:

...\mods\update\x64\dlcpacks\addon_engines\dlc.rpf\x64\audio

& drag & drop them to a Windows folder location of your choice & then open them with Notepad++.

In the '**.nametable**' files you'll see a list of the English names that are included in the '**.rel**' files separated with black background **NUL** characters.

**Example:**

![Nametable Example](https://live.staticflickr.com/65535/50336567251_942d615c19_o.jpg)

You add any new names you have added to the '**.rel**' files in that format with no spaces & ending the line with a NUL character.

**How to create a NUL character:**
To add a **NUL** character using Notepad++ go to '**Edit**' tab > '**Character panel**' (panel box will appear) > Double-click the '**NULL**' at the top in the character column & a black background '**NUL**' will appear wherever the cursor is in the document.

Once you have added all your new names to the '**.nametable**' files for both '**.rel**'s, you are ready to import both the '**addon_engines**' '**.rel.xml**' & '**.nametable**' files files back into the game & test your new add-on vehicle engine sound.

**Import the 'addon_engines' '.rel.xml' & '.nametable' files back into the game:**
-

Now in CodeWalker's **RPF Explorer** once again. track to:

...\mods\update\x64\dlcpacks\addon_engines\dlc.rpf\x64\audio

 - Once there, hit the '**[:shield: Edit mode]**' button (top, middle, right-ish) & confirm entering edit mode by hitting '**[Yes]**'.
 - Right-click within the folder & select '**Import XML...**'
 - Track to the location of your edited & saved '**dlcaddon_engines_game.dat151.rel.xml**' & '**dlcaddon_engines_sounds.dat54.rel.xml**' files
  - Select them & hit '**[Open]**' & they should import (file icon/s turn dark for a sec & then back to normal lighter colour when import is complete)
 - '**.nametable**' files are easy, just drag & drop them (as is), into the same location as the '**.rel**' files using either OpenIV *or* CodeWalker's RPF Explorer. 

If you skipped the **Renaming the replace '.awc' correctly** section above, remember to return to it & complete it.

After that all that's left to do is add your add-on **audioNameHash** ('**v8supercharger**' etc) to a vehicle & test it out ingame :thumbsup:

**Set the '**audioNameHash**' for a vehicle in '**vehicles.meta**':**

**Example:** 
```xml
      <audioNameHash>v8supercharger</audioNameHash>
```