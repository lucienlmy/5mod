**Software Required:**
 -
For this you are going to need a copy of: 

 - [OpenIV](https://openiv.com/)
 - **Codewalker** - Get a new version from the [Codewalker Discord](https://discord.com/invite/BxfKHkk) as the one on this site (v.29) is 2.5 yrs out of date & will ***not*** allow you to export '**.rel**' files to XML.
 - A Text Editor of choice (Notepad will do, but there are many advantages to using something a little more advanced like [Notepad++](https://notepad-plus-plus.org/downloads/)) 
 
**DLC Vehicle Sounds:**
 -
I'll outline the process for the files containing the info for the main body of non-dlc GTA V vehicle engine sounds. For the DLC vehicles, all you have to do is follow the same process, but instead use the DLC counterpart files. They are all named similarly & easy to find in any DLC using OpenIV's **Ctrl+F3** search box (see '**Finding DLC '.rel' Files:**' at bottom of post).

**Instructions:**
 -

**Export 'game.dat151.rel' & 'sounds.dat54.rel' files to '.xml' Using Codewalker's RPF Explorer:**
 - Start up Codewalker & select '**[<<]**' (top right) > '**[Tools...]**' > '**RPF Explorer...**'
 - Wait for the '**RPF Explorer**' to load fully (will say '**File cache loaded**' bottom left) & then navigate to:

..\mods\update\update.rpf\x64\audio\config

**Note:** ...\mods\update\ **update.rpf** \x64\audio\config (***Not*** '...\mods\x64\audio\audio_rel.rpf\config') :thumbsup:

 - Once there, highlight the '**game.dat151.rel**' & '**sounds.dat54.rel**' files using **Ctrl+left-click**.
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
**Find the 'UnkVecData' Values in 'sounds.dat54.rel.xml' to Edit the Engine Pitch:**
 - Now proceed to the '**sounds.dat54.rel.xml**' file.
 - Search for the 'hash_########' value you just copied from the '**game.dat151.rel.xml**' file & you will usually find a few (2 or 3) results.
 - Navigate to the '**hash_########**' result just under the '**<Item type="GranularSound">**' line.
 - From there, scroll down until you find the next '**<UnkVecData>**' line (usually about two pages).
 - The first two values under the '**<UnkVecData>**' line are the engine & exhaust pitch minimum (left value) & maximum (right value).
 - The next two values (usually the same) are the engine & exhaust idle pitch.
 
 **Example:**
 ```xml
   <UnkVecData>
    10.47, 57.76 <!-- Engine & exhaust min & max pitch -->
    15.75, 15.75 <!-- Engine & exhaust idle pitch-->
   </UnkVecData>
```
 - After you make your edit/s, save the file & reimport it back into the game where you got it using Codewalker's **RPF Explorer**.

 -  To get '**Import XML...  Ctrl+Ins**' to appear, hit the '**[:shield: Edit mode]**' button (top, middle, right) & confirm entering edit mode by hitting '**[Yes]**'.

 -  Then **right-click** within the folder > '**Import XML...  Ctrl+Ins**' & select your edited '**.rel.xml**' files
 - File icons in the **RPF Explorer** for the files you are importing will turn dark for a moment until the import is complete.

**Extra:**
 -
 - There are two sets of '**UnkVecData**' values for each engine sound, one for the player vehicle & another in the next '**<Item type="GranularSound">**' section, for the '**STREAMED_VEHICLES_GRANULAR_NPC.rpf**' npc vehicles (ie the sound npc vehicles make when they drive past you)
 - Ideally, you probably want to edit both at the same time. They are not always the same values, so you may have to experiment to see what sounds best. 

 - After that, save the file & then reimport the it back into the game where you got it, using Codewalker's RPF Explorer's right-click > '**Import XML... Ctrl+Ins**'

**Finding DLC '.rel' Files:**
 -
DLC '**game.dat151.rel**' & '**sounds.dat54.rel**' files are prefixed with their dlc name. Like '**dlcjanuary2016_game.dat151.rel**' & '**dlcsmuggler_sounds.dat54.rel**' for example.
Alternatively, searching for '**game.dat151.rel**' or '**sounds.dat54.rel**' will show all of those files & their locations in the game, allowing you to select the ones you want.