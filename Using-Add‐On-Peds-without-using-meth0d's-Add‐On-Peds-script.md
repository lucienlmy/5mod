#### Tired of not getting [**Addon Peds by meth0d**](https://www.gta5-mods.com/scripts/addonpeds-asi-pedselector) to work? 
Pressing L till your fingers bleed? Sad you can't play as your favorite female? 
Suffering from emotional drainage that each update might potentially break this long abandoned script?
>
#### No worries, there's still HOPE! All you need is 5 things »
>- 1. [**This addonmaps dlcpack template (new link)  »**](https://www.mediafire.com/file/nvpyoy6b1lcpn24/addonpeds.zip/file), to be placed in your **```mods\update\x64\dlcpacks```** inside an **addonpeds folder** and of course with the line added to your dlclist.xml in **```\mods\update\update.rpf```**; this will contain your added peds;
>- 2. [**Simple Trainer for GTA V by Sjaak »**](https://www.gta5-mods.com/scripts/simple-trainer-for-gtav), to be placed in your game base folder; this will be the tool to spawn the Add-On ped by entering the name (or, alternatively use Menyoo);
>- 3. [**ReSpawnfix.asi by Unknown Modder, only available inside Grand Theft Space [.NET] »**](https://www.gta5-mods.com/misc/grand-theft-space-net-gts-devs), to be placed in your game base folder; this will prevent the game from crashing when you die as an Add-On Ped;
>- 4. [**Character Swap by Unknown Modder »**](https://www.gta5-mods.com/scripts/character-swap); this will be needed if you want your Add-On ped to be played on missions and have money;
>- 5. stamina and perserverance while you're learning this alternative route;
>
#### For starters »
This guide was written with the informed user in mind. So if you are new to modding GTA V, have no clue what a **dlclist.xml** or **gameconfig.xml** file does and have never added new information like add-on vehicles to your game, I advise you to first read  [**ikt's Quick Guide to modding V »**](https://forums.gta5-mods.com/topic/14693/quick-start-guide-to-modding-grand-theft-auto-v) and add a couple of Add-On vehicles to your game first ^_^
>
#### Inner workings on addonpeds dlcpack »
So, you are still reading? Good. This method needs you to understand a bit more of the inside of a dlc.rpf than the average Add-On vehicle. So here we go. As I basically took the addonpeds\dlc.rpf once created by meth0d, it follows a slightly different hierarchy than your normal dlc:
- **content.xml** in which all files within the dlc.rpf are listed, make an error in this file and you'll get served an error when starting the game saying 'corrupted game info' so when you're making edits to a content.xml and get that, you'll know you've made an error in referring to a file inside the archive;
- **setup2.xml** contains information on how the game should load the dlc. If you want the dlcpack to be loaded more early in the process for example, change sort_order to 0 (first to load right after R* patchdays and archives) or any number;
- **peds.meta** contains the meta lines that control behaviour of the ped. In vanilla this file is called peds.ymt (peds.meta) and V reads it to know how to control the ped. You will be editing this file each time you add a ped;
- **peds.rpf** and **peds2.rpf** and so on and so forth contain the model and texture info that you have downloaded and import here. It is your choice if you just want to use a single archive or several rpf files to make edits easier;
>
#### Two types of Add-On Peds »
When you start downloading peds, you will notice there are two types of Add-On Peds, [streamed »](https://www.gta5-mods.com/player/black-widow) and [non-streamed (normal) »](https://www.gta5-mods.com/player/ben-affleck-w-luxury-clothes-add-on). Follow the links for an example on each.
The streamed peds come with two files and a folder and can most likely be used in cutscenes (so to be played as a character in story mode even) mind you, facial animation will only work on a handful whereas non-streamed 'normal' peds come with four files.
When you rename your ped to your liking always rename all files / folder. Do not rename the files inside the folder of a streamed ped. And best to always use a short name without special characters as you'll be needing to type the name manually in the trainer. So Black_widow, vaasfc3 but do not use a dash - of exclamation ! etc.
>
#### Peds.meta in detail »
Before you start, open the peds.xml file and examine it. It is grouped by different categories and I left in lines from my own pack. Streamed versus normal ofcourse as explained above and also male versus female as they differ in walk style animation. One more thing you'll notice is the hooker_heels for females. When you have used meth0d's before you probably noticed all your peds had male walk style animation AND on certain females the feet sank in the ground. No more I tell you! With the hooker_heels solution this is a thing of the past. So, when you spawn a ped and the feet sink in the ground, use the lines from the hooker_heels (streamed or normal) and fix that! This fix is a courtesy by LeeC.
>
#### For this guide I used [Black Widow by mstfa, which is a streamed ped](https://www.gta5-mods.com/player/black-widow)
>
#### Step 1, download your ped and rename to your choice, open OpenIV and navigate to the addonpeds dlcpack »
![<insert image>](https://cdn.discordapp.com/attachments/534296061888561172/535404201610838026/step1.jpg)
>
#### Step 2, import the ped files into the addonmaps dlcpack, **drag them inside a peds.rpf** »
![alt text](https://cdn.discordapp.com/attachments/534296061888561172/535404212545257472/step2.jpg)
>
#### Step 3, drag peds.meta outside OpenIV for easy editing, copy-paste a new meta line with the new ped name (**select the correct category as explained above!**) and drag the edited peds.meta back into the addonmaps dlcpack and check in OpenIV »
![alt text](https://cdn.discordapp.com/attachments/534296061888561172/535404234167025674/step3.jpg)
>
### Presto, already done. Close OpenIV for safety and go play! 

![alt text](https://cdn.discordapp.com/attachments/534296061888561172/534296240481894410/1.png)
![alt text](https://cdn.discordapp.com/attachments/534296061888561172/534296509231923200/2.png)
![alt text](https://cdn.discordapp.com/attachments/534296061888561172/534296684310691840/3.png)
![alt text](https://cdn.discordapp.com/attachments/534296061888561172/534296723347079168/4.png)


#### This is just a workaround until someone else steps up and creates an alternative script
#### and adds a proper selection menu, adds  clothing and props selection to go with it
>
>
#### Short information messages if you're still reading »
- do you still get 'Invalid Model' when trying to spawn your ped? Then visit my forum profile page as you probably need a custom **gameconfig.xml** and/or HeapLimitAdjuster;
- **animation walk styles** can be changed over ```peds.meta```, [see here for a full list by Alex Guirre](https://alexguirre.github.io/animations-list/) is also included in the readme.txt;
- **ped voice groupes** can be changed over ```peds.meta```, a full list is included in the readme.txt;
- always defragmenting your dlcpack is good business, so is backing up your entire dlcpack from time to time;
- important **gameconfig.xml** information when your game crashes when you're adding too much model information:
>- <PoolName>Peds</PoolName> <PoolSize value="450"/>
>- <MaxTotalPeds_Base value="200"/>
>- <PedMemoryMultiplier value="500"/>
>- <MaxPedModelInfos value="900"/>
>- <MaxExtraPedModelInfos value="800"/>
>
>
ReNNie, 01/19/2019