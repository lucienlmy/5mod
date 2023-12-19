Original post by a63nt-5m1th on GTA5-Mods

***


**Software Required:**
 -
For this you are going to need a copy of: 

 - [OpenIV](https://openiv.com/)
 - **Codewalker** - Get a new version from the [Codewalker Discord](https://discord.com/invite/BxfKHkk) as the one on this site (v.29) is 2.5 yrs out of date & will ***not*** allow you to export '**.rel**' files to XML.
 - A Text Editor of choice (Notepad will do, but there are many advantages to using something a little more advanced like [Notepad++](https://notepad-plus-plus.org/downloads/)) 

**DLC Vehicle Sounds:**
I'll outline the process for the files containing the info for the main body of non-dlc GTA V vehicle engine sounds. For the DLC vehicles, all you have to do is follow the same process, but instead use the DLC counterpart files. They are all named similarly & easy to find in any DLC using OpenIV's **Ctrl+F3** search box (see '**Finding DLC '.rel' Files:**' at bottom of post).

**Instructions:**
 -

**Export the  'game.dat151.rel' & 'sounds.dat54.rel' files to '.xml' Using Codewalker's RPF Explorer:**
 - Start up Codewalker & select '**[<<]**' (top right) > '**[Tools...]**' > '**RPF Explorer...**'
 - Wait for the '**RPF Explorer**' to load fully (will say '**File cache loaded**' bottom left) & then navigate to:

..\mods\update\update.rpf\x64\audio\config

**Note:** ...\mods\update\ **update.rpf** \x64\audio\config (***Not*** '...\mods\x64\audio\audio_rel.rpf\config') :thumbsup:

 - Now highlight the '**game.dat151.rel**' & '**sounds.dat54.rel**' files using **Ctrl+left-click**.
 - Right-click on one of the files & select '**Export XML... Ctrl+S**' & select a folder location to export the files.

**Search the 'game.dat151.rel.xml' file for a Vehicle Name:**

 - Open both the '**game.dat151.rel.xml**' & '**sounds.dat54.rel.xml**' files with a Text Editor & then move to the '**game.dat151.rel.xml**' file.
 - Hit '**Ctrl+F**' & use the search box to search for a vehicle name.
 - Once you've found the vehicle, it should look something like this:

**Example:**
```xml
  <Item type="Vehicle" ntOffset="369587">
   <Name>rocoto</Name> <!-- vehicle name here -->
   <Unk00 value="0x90005A68" />
   <Engine>hash_77F193EC</Engine>
   <EngineGranular>hash_9A96C7AD</EngineGranular>
   <Horns>hash_134DA50D</Horns>
   <DoorOpen>hash_1D48FFC4</DoorOpen>
```
**Note:**
Just a word of warning, the three sections ('**Vehicle**', '**VehicleEngine**' & '**VehicleEngineGranular**') do not have to be next to each other (they *usually* are, just '**VehicleEngine**' & '**VehicleEngineGranular**' swapped around sometimes), but the connections between the three sections are formed by the name/hashes directly under the '**Vehicle**', '**VehicleEngine**' & '**VehicleEngineGranular**' lines, *not* their order in the file.
For the most part, you'll probably find the right sections just under each other, but if for some reason that doesn't work or you prefer to confirm beforehand, use the '**Troubleshooting:**' post below this one to be sure you have the right three linked sections.

**Right, back to the tutorial:**

 -  From the vehicle name, navigate down one or two sections (it varies), until you find the next '**VehicleEngineGranular**' line, like this:

**Example:**
```xml
  <Item type="VehicleEngineGranular" ntOffset="369608"> <!-- This line -->
   <Name>hash_9A96C7AD</Name>
   <Unk00 value="0xAAAAA905" />
```
 - Four lines under the '**VehicleEngineGranular**' line you will find a '**<EngineAccel>**' line
 - Copy whatever hash is in the '**<EngineAccel>**' line (in this case '**hash_4173DD5C**'):
 
**Example:**
```xml
  <Item type="VehicleEngineGranular" ntOffset="369608"> 
   <Name>hash_9A96C7AD</Name>
   <Unk00 value="0xAAAAA905" />
   <MasterVolume value="0" />
   <EngineAccel>hash_4173DD5C</EngineAccel> <!-- copy the hash_######## part of this line -->
   <ExhaustAccel>hash_A5C6E3AA</ExhaustAccel>
   <Unk04 value="0" />
   <Unk05 value="0" />
``` 
**Find the Name of the Engine Sound ('.awc') File in 'sounds.dat54.rel':**
 - Now proceed to the '**sounds.dat54.rel.xml**' file.
 - Search for the 'hash_########' value you just copied from the '**game.dat151.rel.xml**' file & you will usually find a few (2 or 3) results.
 - Navigate to the '**hash_########**' result just under the '**<Item type="GranularSound">**' line.
 - A few lines under that in the '**<ContainerName>**' lines you will find the name of the '**.awc**' the vehicle uses for it's engine sound:

**Example:**
```xml
  <Item type="GranularSound">
   <Name>hash_4173DD5C</Name> <!-- Find this result under 'GranularSound' & then look to the 'ContainerName' just below it to find the '.awc' engine sound file name -->
   <Header>
    <Flags value="0x00208001" />
    <Flags2 value="0x9555AAAA" />
    <Category>hash_F7C35252</Category>
    <Unk18 value="150" />
   </Header>
   <WaveSlotIndex value="0" />
   <Wave1>
    <ContainerName>streamed_vehicles_granular/sportscar_4_eur_4_cyl</ContainerName> <!-- The Rocoto uses 'sportscar_4_eur_4_cyl.awc' -->
    <FileName>engine_accel</FileName>
   </Wave1>
   <Wave2>
    <ContainerName>streamed_vehicles_granular/sportscar_4_eur_4_cyl</ContainerName>
    <FileName>exhaust_accel</FileName>
   </Wave2>
   <Wave3>
    <ContainerName>streamed_vehicles_granular/sportscar_4_eur_4_cyl</ContainerName>
    <FileName>engine_decel</FileName>
   </Wave3>
``` 

That's it, you've got your engine sound to edit (in this case '**sportscar_4_eur_4_cyl.awc**'). 

**Find '.awc' in Game Files using OpenIV:**
Use '**Ctrl+F3**' in OpenIV to search for it by name, export the '**.awc**' to openformats using the OpenIV right-click menu & edit the files with your Audio Editor of choice before reimporting the '**.oac**' back into OpenIV via drag & drop :thumbsup:

**Finding DLC '.rel' Files:**
DLC '**game.dat151.rel**' & '**sounds.dat54.rel**' files are prefixed with their dlc name. Like '**dlcjanuary2016_game.dat151.rel**' & '**dlcsmuggler_sounds.dat54.rel**' for example.
Alternatively, searching for '**game.dat151.rel**' or '**sounds.dat54.rel**' will show all of those files & their locations in the game, allowing you to select the ones you want.

**Extra:**
 -
All the '**<ContainerName>**' lines for any one ''**<Item type="GranularSound">**'' section (in '**sounds.dat54.rel.xml**')  *need* to be the same, you can *not* mix & match lines from different '**.awc**' files or you will get a silent engine in-game:

**Example** (broken = silent engine in-game): 
```xml
  <Item type="GranularSound">
   <Name>hash_4173DD5C</Name>
   <Header>
    <Flags value="0x00208001" />
    <Flags2 value="0x9555AAAA" />
    <Category>hash_F7C35252</Category>
    <Unk18 value="150" />
   </Header>
   <WaveSlotIndex value="0" />
   <Wave1>
    <ContainerName>streamed_vehicles_granular/muscle_car_2_us_v8</ContainerName> <!-- This 'muscle_car_2_us_v8' here will cause silent engine in-game. It needs to be 'sportscar_4_eur_4_cyl' like the rest -->
    <FileName>engine_accel</FileName>
   </Wave1>
   <Wave2>
    <ContainerName>streamed_vehicles_granular/sportscar_4_eur_4_cyl</ContainerName>
    <FileName>exhaust_accel</FileName>
   </Wave2>
   <Wave3>
    <ContainerName>streamed_vehicles_granular/sportscar_4_eur_4_cyl</ContainerName>
    <FileName>engine_decel</FileName>
   </Wave3>
```

**Mixing & Matching Engine & Exhaust Sounds from Different Vehicles:**

It's possible to mix & match sounds from different vehicles as long as you use the:
```xml
   <EngineAccel>hash_4173DD5C</EngineAccel> 
   <ExhaustAccel>hash_A5C6E3AA</ExhaustAccel>
```  
lines in '**game.dat151.rel.xml**' to do so. 

Just change the '**hash_########**' value in the lines to that of another vehicle:

**Example** (different exhaust sound):
```xml
   <EngineAccel>hash_4173DD5C</EngineAccel> 
   <ExhaustAccel>hash_1BE8F4F3</ExhaustAccel>
```

**Note:**
Results may vary with mixing & matching due to unknown audio flags, but it will work at least & you are free to experiment if you like.