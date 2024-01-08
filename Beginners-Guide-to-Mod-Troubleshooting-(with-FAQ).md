So I will start this off on the assumption that you have watched Figure8's video on how to install mods and are somehow still having issues with your game. If you haven't watched it, I recommend you do so as it covers the simple fixes for the most common mistakes when modding.

https://www.youtube.com/watch?v=N0ovURiaTtE&ab_channel=Figureight

The purpose of this guide is not to tell you what you need to do in order to fix your game, but to teach you the basics of how the game works, why certain errors occur, and allow you to begin working out for yourself why things break, and how to fix them on your own. I will also preface this that this guide will be heavily biased towards vehicles, as that’s where my experience lies. I welcome anyone with map, ped or weapons experience chime in with new sections that I can add.

I will first provide an overview of the workings of various aspects of the game, before going into an FAQ covering a lot of stuff that I have seen asked a lot, particularly by new modders. Please read the main body before going to the FAQ as a lot of questions should be answered by the over-view. I will finally cover basic troubleshooting techniques should the FAQ not cover your issue.


**Package Installers**

OIV Package Installers are both a blessing and a curse in equal measures. When they work they make mod installation significantly easier, however when they don't they can irreparably break your game.
For those that don’t already know, a .oiv is just a zip file in a pretty dress. You can open and navigate an oiv file in exactly the same way as any other zipped file in windows explorer/winzip/7zip/etc. 
Knowing this information, you can go into an oiv file and you will see 2 files and a folder:  Content, icon.png and assembly.xml. The icon is pretty self explanatory, the stuff we are interested in is the Content and assembly. 
Opening the assembly file you are greeted with an xml file containing lots of file names and addresses, that look a bit like this:

<add source="gc\gameconfig.xml">\common\data\gameconfig.xml</add>

To anyone that has never used xml before (best get used to it, GTA uses a lot of it), this can be broken down pretty easily:

The <add> tag tells the package installer to add the “source” gameconfig.xml found in the gc folder of the content folder into the path \common\data\gameconfig.xml

And that’s it, that’s all the OIV does, over and over again until the final line is complete. There is nothing stopping you from doing the same thing, manually, or, alternatively, commenting out lines you don’t want to complete using the xml <!--comment--> tags. Personally, I tell oiv packages to ignore the above gameconfig line as I have my own already, and its often that causing the issue that package installers have.


**Gameconfig**

That leads on nicely to talk about the gameconfig. As the name implies, the gameconfig is the configuration that the game will use in order to run. It is a large file full of references and numbers that few have looked at (myself included) and even less have mastered (not me). 
All of these numbers define baseline population densities, traffic spawning habits, scripts, cutscenes etc… All you need to know that the correct game config is critical for launching your game without issue.
Everyone’s machine is different, and different configs will yield different results for different people. Don’t go around saying someone’s config is terrible when it crashes your game, it just didn’t work for your specific setup. 
The trick here is to keep experimenting with different configs until you find one that both launches your game and is stable when playing. Once you’ve found one that works for you, with a traffic setup that works well with your play style (the best configs often come with multiple traffic levels), stick with it, hit the follow updates button and stay with that config until it starts to break again.


**Traffic**

Traffic seems to be a common point of enquiry when I see new mods, especially larger packs come out; “Will this show up in traffic when I install it?” Not if you didn’t change the traffic files it won’t.
The vehicles that spawn in traffic is defined by two files, the popgroups.ymt and popcycle.dat. 
Popcycle.dat is a population file that defines which Population groups appear in which areas at any given time of day. As you scroll down the file you will see it is split into groups defined by areas of the map (Alta, Strawberry, Davis etc…). Within each of these map areas are 12 lines of names and numbers. Each of these lines represents a two hour period throughout each in-game day, starting at 00 and ending at 22. As you go across each line, you first have the annotated columns defining a few basic values, these are things like the maximum number the game will attempt to spawn on the road, how many of them will be parked, how many should get reserved for ‘scenario’s as well as similar values for peds. 
With those numbers defined, the file then defines the popgroups that it should pick from to spawn, first the peds, then vehicles. Each of these popgroups named will have a 2 digit number that is a percentage weighting for that given group. For example, VEH_POOR 50 means that 50% of the traffic in the given area will be from the VEH_POOR popgroup at that given time of day. The popcycle file is quite complex, and there is little reason for it to be modified unless you want to alter the way that vehicles/peds are grouped.
Popgroups however, is much more interesting to us, that defines which peds and vehicles are within each of the groups that the popcycle requests. In the file you will see each popgroup named as an xml <item> , and within that, the names of all the peds/vehicles within that group. Any item that is within a given popgroup has a random (weighted) chance of being spawned as the game requests something from that group. For memory saving, the game will keep spawning that vehicle until the maxnum defined in vehicles.meta has been reached, or you’ve moved to an area where that vehicle is no longer meant to spawn. 
You can, theoretically, add any vehicle you want to the popgroups, however you need to be wary of LODs, as that can cause major instability.

**LODS**

LOD stands for Level of Detail, and is a games way of saving memory when running particularly busy environments. Game models these days have 10’s of thousands of polygons, often taking more than a Megabyte of memory for a single vehicle. Even when these vehicles take up only a few pixels on your monitor, the entire thing is still rendered, even though none of that detail can be seen. LOD’s on a vehicle are a low-poly version of the original model, with a significant reduction in the amount of polies loaded in, depending on how far away it is. GTA uses L0-L4. L0 being the original, unmodified model, used when the player is right next to the car or driving it, down to L4, which is basically a box with headlights and wheels. 
GTA is a very memory intensive game, and doesn’t like it when you run out. Spawning vehicles without LODs is a very quick way to ramp up your memory usage without any real effort, and will easily cause ‘random’ crashes whilst playing. 
LODs are a very time consuming process for mod-makers, so if they are included, the modmaker will often make a point of stating that the mod includes LODs, allowing you to spawn it without fear in traffic. If you are unsure, you can go to the vehicles.rpf folder of the mod, and you will see a model.yft and model_hi.yft. As a general rule, if the file size of both is the same, they don’t have LODs, if _hi.yft is much larger, then it has very well optimised LOD’s, if they are similar or the _hi.yft is smaller, then it may have LOD’s, but not very well optimised, use those with caution in traffic. 


**DLCPacks**

The vast majority of mods you deal with will come as part of a DLCPack. There is a common misconception that there is a hard limit on the number of DLCPacks you can install, this is absolutely not true. With the packfile limit adjuster, all such limits are removed.
DLCPacks were Rockstars way of easily adding new online content without having to modify core files.  In order to find the files, the game needs to be told where to look. The DLCList is where the folders are defined, if the name here is not identical to the name in the dlcpacks folder, the game won’t find it. Another common error is the wrong folder being placed within dlcpack. In that first folder must be a dlc.rpf. If there is another folder within, then the game again will not find it.
Inside the DLC.rpf you have a content and setup file, these both tell the game what is inside this dlc, and what types of data it is. For vehicles you’ll generally have 5 data files and the models, textures, and tuning parts. 

**Vehicle Files**

Vehicles have 5 meta files that are needed for them to work (Well, 3, but most have 5); carcols, carvariations, dlctext, handling and vehicles. I have no idea what dlctext does, as far as I can tell it is identical in every dlcpack vehicle, so I assume it’s some basic running file. 
Carvariations and Vehicles meta files are absolutely critical, without them the car wont spawn.
The vehicles meta file contains all kinds of data and references about the vehicle itself; the vehicles class, the camera type when driving it, what audio, handling and modkit it should use, how many are allowed to spawn in traffic (the maxnum mentioned earlier) and all kinds of other useful things that can be used to tweak the cars behaviour. 
Carvariations tells the game information about the car when it spawns in, colours, extras that should spawn, the licence plates it should have, and the modkit to be used if it needs one. This is how the game doesn’t spawn weird and wonderful colours in traffic, because each vehicle has a specific colour set to choose from, much like manufacturer paint codes in real life. The colours are defined by a series of numbers, there are plenty of resources online to tell you what colours each number is if you want to start modifying this.  
Handling is another critical file, if the vehicles.meta doesn’t point to an already existing handling ID. As the name implies, this file just defines how the car behaves on the road, speed, agility, weight etc… are all defined by the various values in here, again, lots of good resources to go into more detail than I have space for.
Finally, carcols defines the tuning parts included with the car and how they appear when added to the vehicle, the modkit defined in carvariations should point to the same modkit defined in here. Within the carcols file you will see a long list of all the possible tuning parts you can get for the vehicle, as well as the stat modifiers and light coronas if need be. There isn’t a lot of information online about the carcols file, but once you’ve read a few of them it starts to make more sense. Basically, for a given model, the game is told what ‘bone’ to attach the vehicle to, and what parts, if any, need to be turned off so as not to cause a conflict. Once you gain confidence with this you can start changing the parts that get added, removed or modified in your vehicle tuning menus (I like to remove bumpers on older stuff)


**Modkits** 

Another common complaint is tuning parts not working for a car; this is because of a modkit conflict.  In the carcols file a unique “ID Value” is assigned to the named modkit. Should two different modkits share an ID value, the last one loaded will take precedent and the other will break, and will have no tuning at all. To get around this, you simply need to change the ID of the broken vehicle to something known to be vacant, sometimes this is just trial and error until the modkit works.
As you may be aware, there is an upper limit on the number of modkits allowed, this is often misattributed as 65,535. While you are able to use modkit ID’s up to that value, the old limit of 1023 is still in place, should an ID higher than that be used, the modkit will still work, but it will wrap around to take a modkit ID below 1023, wiping out whatever modkit was in the space it wrapped to. 
Rockstar are currently up to 445 with their own modkits, and many modders use higher numbers to future proof their mods. I have found that in most instances, the 500-800 range has been avoided by most vehicle mods, and is a generally safe area to change your ID to. 
Many vehicle creators do break this rule and go above the 1023 limit as it almost guarantees that their mod will always work. I personally make a habit of going into the carcols of any new mod I download to check the value is good.


**Good Practice**

Just a brief section on good practice when modding your game, to help you prevent issues, and quickly find solutions when you do inevitably have a problem. 
1)	Back up everything. Goes without saying, whenever the game is working, stable and in a state that you are happy with, back up the entire GTAV folder, second hard drive, another folder, whatever, keep that badboy safe in case things go really wrong.
2)	Use the mods folder. Its there for a reason, if something is broken and you don’t know why, by using the mods folder you can either delete the file or replace it with the original game files to see if that fixes it.
3)	Never install more than one mod at a time. This is a more common mistake than you would realise, and makes troubleshooting much more difficult than it needs to be. Install a mod, launch the game, confirm it works, then close the game and move onto the next one. 

**FAQ**

“My game crashes during the loading screen”
Usually caused by a gameconfig not fit for your game, try changing the config for something else and see what happens. If that doesn’t fix the problem then you can use the OpenIV.log to see what the last item openiv tried to load was. If the last line in the file is a mod you installed, chances are that is the cause of the problem.

“My game crashes within a few seconds of loading into SP”
More often than not a memory issue, try turning down your graphic settings. Sometimes if the graphics are too intense for your computer, especially if you have Reshade and/or ENB, that can cause a memory leak that, as mentioned previously, can cause GTA to throw its toys out the pram. Disable ENB and Reshade (there are hotkeys for this in game) and see if that fixes the crash. 

“My game crashes as soon as I enter a vehicle”
The vehiclelayout for that vehicle is broken. Double check the vehicles.meta file to ensure it is pointing to a valid layout

“My game crashes as soon as I spawn a vehicle”
The handling file for that vehicle is broken. If it doesn’t have one, make sure the handling pointed to in vehicles.meta is valid.

“My game crashes randomly as I’m driving around”
Either your graphics settings are too high, but not so high it crashes immediately, or, more likely, you have vehicles without LOD’s spawning in traffic. Either way the game ran out of memory.

“Textures keep glitching/disappearing/going really low quality”
The game is desperately trying to save resources as there are too many assets loaded in the map. If you have a map enhancement mod that adds more detail to the world, or increased traffic, consider turning them off

“My modded vehicle will not spawn in game”
Depending on how it doesn’t spawn can be a few different causes. If you can’t find it at all in menyoo or addon spawner then the mod didn’t load correctly. You can double check openiv.log to for the dlcpack to see if the vehicles.rpf within the file got loaded in game. If it didn’t, then you need to check your dlclist entry, or the dlc.rpf is the first file in the dlcpack folder. If it did load, you need to check your meta files.
If the vehicle does show in your menu’s, but the model doesn’t load, then the model file is not being found, check the file names.

“My modded vehicle has no tuning/menyoo crashes when I select wheels”
The modkit has been broken by a conflict, read the modkit section again.

“I replaced a model but the original model keeps spawning in”
Rockstar often uses the dlc_patch and patchday dlc’s to make minor changes to their own vehicle models. If you replaced the original yft files and not the patched files, then the patched ones will take precedence.

 **Troubleshooting**

If you’ve tried the above advice and still get no results, game crashes or other weird behaviour, here is the catch all troubleshooting routine that I follow when things have gone badly, badly wrong.

Before doing anything, try verifying your game files. Its very easy to accidentally delete a critical file without realising. Sometimes a simple verification can fix it. If it doesn’t, read on.

Preface: I will say rename a folder a lot here. When I say rename, just change it to something other than what it is in order to confuse the game enough to not load it, i.e. rename mods to xmods or something, something you can easily change back, as you’ll be doing it a lot.

You need to identify the specific file that is causing you problems, if de-activating the last mod you installed didn’t work, then do the following procedure:

Rename your mods folder and try launching the game to confirm it is definitely a mod and not a script or something else causing you issues. If the game launches and plays correctly quit the game and name it back. If it still doesn’t launch, name it back and then rename your scripts folder. If that doesn’t work then your game is fully broken, you may need to re-install and start from scratch.

Assuming the problem was in your mods folder, go inside, rename x64 and launch the game. If it doesn’t load and play, quit, name it back, rename update.rpf. Whichever change allows the game to launch correctly, name it back, and go into that folder. Repeat the process until there are no folders left to rename. If you have reached a dlcpack, try deactivating that specific pack in dlclist.xml and launching the game to confirm it works. If you have reached a file within update.rpf, you can try replacing the problematic files with those from the games original update.rpf.

It is a laborious process going through all this, but it will absolutely find your issue every single time.


**Final Word**

As mentioned at the beginning of this guide, this barely scratches the surface of how the game works, but the information I have provided here gave me enough groundwork to solve most issues that I come across on my own, and I hope will allow you to do the same. Anyone with more expertise in some areas than myself, please feel free to add more and I can edit my own posts with the info you provide. Anything that can be added to the FAQ is also welcomed, if you can answer it yourself, please do, if not, I will try to answer as best as I can.