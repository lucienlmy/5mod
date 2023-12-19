Original post by [Reyser](https://www.gta5-mods.com/users/Reyser) at GTA5-Mods.com

***


Hello guys! This tutorial will help you to make the tedious GTA Modding a bit easier :)

| If you want a simplified (`With Screenshots`) tutorial for vehicles: [:arrow_right: Click me! :arrow_left: ](https://forums.gta5-mods.com/post/29728) 
|:-:|
| **Some TIPS to improve your game PERFORMANCE: [:arrow_right: Click me! :arrow_left: ](https://forums.gta5-mods.com/topic/11455/tips-vehicle-and-script-installed-mods)**
| **Spanish Translation / Traducción Española: [Click me! / Haz clic! 🇪🇸 ](https://forums.gta5-mods.com/post/28736)**

**`WARNING`**: By reading this tutorial, you're accepting to reject any accusation against this tutorial or his owner for any damage you can cause to your game (Do it at your own risk). If you didn't read this before, do not relieve yourself from guilt. That doesn't mean that you can't ask for help.

 
| INDEX
|:-:|

- `Knowledge` **What I need to know before asking for help**
  - *How can I fix this error?*
  - *How can I spawn ADD-ON Vehicles or Weapons?*
  - *Which bugs can do my life harder?*
  - *Why my car has no sound?*
  - *Why my game starts crashing when I try to add a new Add-On Folder to DLCPACKS?*
  - *Why my game crashes when I try to go into an Add-On vehicle?*
  - *Where I can find the DATA for each car I want to put as Add-On?*
  - *My vehicle have some strange/missplaced corona's on headlights and taillights, how I fix that?*
- `Knowledge` **What I need before start using this method**
- `Knowledge` **What contains Add-On/Replace Base Folder?**
  - Vehicles
  - Weapons
- `Tutorial` **CREATE YOUR OWN ADD-ON VEHICLES PACK**
- `Tutorial` **REPLACER to ADD-ON Vehicles**
- `Tutorial` **ADD-ON to REPLACER Vehicles**
- `Tutorial` **REPLACER to ADD-ON MELEE Weapons**
- `Tutorial` **ADD-ON to REPLACE MELEE Weapons**

**___________________________________________________________________________________________________________________________________________________________________________**

| `Knowledge`: **What I need to know before asking for help?**
|:-:|

***How can I fix this error?***

- **`ERR_FIL_PACK_1`:** The total of vehicles that the game try to load is higher than the default limit, or you're using a **SCRIPT** mod that's  incompatible with the most recent game version.
***How to fix that?*** Try to use one of the "***gameconfig.xml***" available on main **GTA5-Mods** website, or check that all your **SCRIPT** mods are compatible with the most recent game version.
- **`ERR_FIL_PACK_3`:** The size of 1 or more DLC's is higher or close to 4GB. 
***How to fix that?*** Defragment "***vehicles.rpf***" and "***dlc.rpf***" files from the DLC/'s that's causing that error respectively. If this does not work it means that one or more of your ***dlc.rpf*** files have already reached a size limit and you'll need to move some mods to a brand new DLC folder.

**How can I spawn ADD-ON Vehicles or Weapons?**
- If **vehicle** files are called "**chevrolet.ytd/.ytf**", in-game, use a **trainer** like **[Enhanced Native Trainer](https://es.gta5-mods.com/scripts/enhanced-native-trainer)** to spawn them. In this case, spawn will be "**chevrolet**".
- **For weapons**, you will need to buy them in a **Ammunation Store**, can't be spawned (or I don't know how) through a Trainer.

**Which bugs can do my life harder?**

- ***Carcols.meta/Carvariations.meta ID's:*** Try changing ID's in both files (If ID is 900, try 953 and other ID's) to see if this helps Tuning Parts working again. Since the DOOMSDAY game update, the limit of IDs is 32767.
- ***Bad edited files/Incorrect name's:*** Be sure you edited all files correctly, without mistakes, sometimes that's the problem (Using **XML Tools** with Notepad++ you can find if you did any mistake opening/closing tags (Example of a tag: `<Item>`).

**Why my car has no sound?**
- ***In "vehicles.meta" file:*** Check if "***AudioNameHash***" tag is like "***<AudioNameHash />***". If yes, then change it to "***<AudioNameHash>VEHICLENAME</AudioNameHash>***", where "***VEHICLENAME***" is the name of the vehicle you like the sound of and you want to use it for your Add-On vehicle.

**Why my game starts crashing when I try to add a new Add-On Folder to DLCPACKS?**

- ***No worries about that:*** Probably you reached the limit of vehicles added to the game files. You can easily fix that using the gameconfig mentioned below (***"What I need before start using this method" section***).

**Why my game crashes when I try to go into an Add-On vehicle?**

- ***Vehicle Layouts:*** The game tries to find the correct layouts for the car you spawned but it doesn't find them, so the game crashes because there's no important information.
 
  ***How to fix that?*** You just need to see in which original game car is based the Add-On vehicle you made, look at the "***vehiclelayouts.meta***" file located to the path where's the original game vehicle, take the info related to it and add it to respective TAGS into the "***vehiclelayouts.meta***" file located in your Add-On files. 

  That should fix the problem if you did all correctly.

**Where I can find the DATA for each car I want to put as Add-On?**

- ***handling.meta*** and ***vehicles.meta:*** The main ones are located on `"/update/update.rpf/common/data/handling.meta"` and `"/update/update.rpf/common/data/levels/gta5/vehicles.meta"`, but in case that data is not located in any of both files, you'll have to check the content of every one of that files into each folder inside `/update/x64/dlcpacks`.
- ***carcols.meta***: You'll have to check every one until you find the correct/needed data for your car. Be sure to check first ***carcols.ymt*** too, which is located in `/update/update.rpf/x64/data`.
- ***carvariations.meta***: You can take any of the available ones and change just the lines needed (Always change the line that contains the car name with the new one, and if car does not have tuning parts in `<kits>` section, change the line inside it to `<Item>0_default_modkit</Item>`.)

**My vehicle have some strange/missplaced corona's on headlights and taillights, how I fix that?**

- That's pretty easy, just open your ***carvariations.meta*** file with Notepad++ or any other text editor and replace the line similar to `<lightSettings value="918" />` ("918" value can be another value in your case) with `<lightSettings value="0" />`. This will remove that shit tailights and will align headlights.

| `Knowledge`: **What I need before start using this method?**
|:-:|

- [OpenIV](http://openiv.com/) ***(Mandatory)***
- [NVE's Gameconfig](https://www.razedmods.com/gta-v) ***(MUST-HAVE to avoid game crashes)***. You will download the full mod but you only need to get the gameconfig from the OPTIONALS folder that's inside the package. Has been hard tested and works perfectly fine in every case.
- [Notepad++](https://notepad-plus-plus.org/download/v6.9.2.html) or any other text editor ***(Mandatory)***
- ****Keep calm**** during the process ***(Mandatory)***

| `Knowledge`: **What contains Add-On/Replace Base Folder?**
|:-:|

| File Name | Description | Knowledge |
|:-|:-:|-:|
|  | **VEHICLES** |  |
| Vehicles DLC Folder | *You'll need to edit normal META files and add vehicles files as always, but also edit "***content.xml***" file each time you add Tuning Parts for any car.* | Basic |
| Vehicles DLC Folder **#:two:** | You won't need to edit "***content.xml***" file. That's because with this method you only need to put tuning part files (**NO** entire **`vehiclename_mods.rpf`** files, **YES** **`.ytd/.ytf`** one's) on **`tuning_mods.rpf`** file. | Medium |
| Vehicles DLC Folder **#:four:** | Is almost the same as the first one, **BUT**, with this, you'll be able to use ***MPLUXE*** vehicles as Add-On's, like ***Pagani Huayra*** by ***Vans123***. **Also**, now you can add vehicles from ***MPHEIST***, like ***M1116 Humvee*** by ***SkylineGTRFreak*** without crashes and totally functional. That's something that with the first one you can't do, otherwise your game will crash. | Advanced |
|  | **WEAPONS** |  |
| Weapons DLC Folder | Here you can put ***melee weapons***. Don't try with gunfire weapons, won't work.  | Basic |
| **Melee** Weapons DLC Folder | Same as before, but this one is provided by @yeahhmonkey and ***should work better***. | Basic |
| **Assault** Weapons DLC Folder | Here you can put **only Assault (gunfire)** weapons. Again provided by @yeahhmonkey. | Basic |

----

Before you use the tutorial below, remember that if you want to convert a **"mpluxe"** Replacer car mod like **Pagani Huayra by Vans123** to an Add-On, **you should use "Vehicles DLC Folder #:four:" from my [Add-On / Replace Base Folder](https://es.gta5-mods.com/tools/add-on-replace-base-folder) mod. (MOST RECOMMENDED OPTION)** 

**___________________________________________________________________________________________________________________________________________________________________________**

| `Tutorial`: **CREATE YOUR OWN ADD-ON PACK** 
|:-:|

**`BEFORE YOU START:`** If is the first time you will do an Add-On Pack, follow all the steps below. When you complete that, verify that your Add-On is working fine before you add more vehicles into it.

**`IF YOU ALREADY HAVE AN ADD-ON WHERE YOU WOULD LIKE TO ADD MORE CARS:`** In that case, just start directly from the **Step :six:** (`Don't forget to read the WARNING that's just above this Step`). 

**Step :one::** **[Download this file as a base for your Add-On's](https://es.gta5-mods.com/tools/add-on-replace-base-folder).**

**Step :two::** Once downloaded, unzip to anywhere you want.

**Step :three::** Now, open **OpenIV**, go to "`/mods/update/x64/dlcpacks/`", create a **new folder** called as you want (I usually call my packs as "**A2NS**", "**A2NS2**", "**A2NS3**", etc) and put inside the "**dlc.rpf**" file.

**Step :four::** Go back to "`/mods/update/`". Now, go to "`/update.rpf/common/data/`" and export "**dlclist.xml**" to anywhere you want on your system.

**Step :five::** Use a text editor as **[Notepad++](https://notepad-plus-plus.org/download/v6.9.2.html)** and edit the file with the next line (Change ***FOLDERNAME*** to the name you put to your DLC BASE Folder):

For "**dlclist.xml**": 

		<Item>dlcpacks:\FOLDERNAME\</Item>        

And now, save changes and put it back to directory mentioned in **Step :four:**.

**IMPORTANT: Edit "content.xml", and "setup2.xml", changing each "FOLDERNAME" word that you find in each file with the word you use as name for your Add-On's folder. Else, your game will crash.**

**Now you have a BASE folder to put replace cars files and data inside as Add-On's.**

**`WARNING:`** Before that Step, if your car's already renamed or the name of his files is different to any other car from the game, you don't need to rename them again.

**Step :six::** Is the moment to put files into their respective directories. Rename "**car.ytf/.ytd**" files, for example "**chall.ytd/.ytf**" (Chall = Challenger), and put them into "`/FOLDERNAME/dlc.rpf/x64/vehicles.rpf`". Do the same process with "**car_mods.rpf**" files, but put them into ""`/FOLDERNAME/dlc.rpf/x64/vehiclemods`" (Don't forget to rename files inside "**car_mods.rpf**", otherwise, they'll conflict with the replacer car tuning parts).

**Step :seven::** Add **DATA** from the new car **(if the car you want to put as Add-On didn't have data when you downloaded it, take data from the original game car that it replaces)** to "**vehicles.meta", "carcols.meta", carvariations.meta**" and "**handling.meta**", which located in "`/FOLDERNAME/dlc.rpf/data/`" editing them with any text editor (This path is supposed to be the place where the DATA files (.meta) of your Add-On should be).

**Step :eight:** (SKIP this if your car doesn't have Tuning Parts): Once you did steps above, if some of the cars you added have **Tuning Parts** (car_mods.rpf), now go back to "`/FOLDERNAME/dlc.rpf/`",  export "**content.xml**" file, edit with **Notepad++** or any other editor and add these lines **to their respective section:**

For "**<dataFiles>**" section:

		<Item> 
	          <filename>dlc_FOLDERNAME:/%PLATFORM%/vehiclemods/car_mods.rpf</filename> 
	          <fileType>RPF_FILE</fileType> 
	          <locked value="true"/>
	          <disabled value="true"/>
	          <persistent value="true"/>
	          <overlay value="true"/>
	        </Item>

For "**<filesToEnable>**" section:

		<Item>dlc_FOLDERNAME:/%PLATFORM%/vehiclemods/car_mods.rpf</Item>        

***Finally, if you did all correctly, you can try your new Add-On cars ;)***

**___________________________________________________________________________________________________________________________________________________________________________**

| `Tutorial`: **REPLACER** to **ADD-ON** Vehicles
|:-:|

**Step :one::** **[Download this file as a base for your Add-On's](https://es.gta5-mods.com/tools/add-on-replace-base-folder).**

**Step :two::** Once downloaded, unzip to anywhere you want.

**Step :three::** Now, open **OpenIV**, go to "`/mods/update/x64/dlcpacks/`", create a **new folder** called as you want and put inside the "**dlc.rpf**" file.

**Step :four::** Go back to "`/mods/update/`". Now, go to "`/update.rpf/common/data/`" and export "**dlclist.xml**" to anywhere you want on your system.

**Step :five::** Use a text editor as **[Notepad++](https://notepad-plus-plus.org/download/v6.9.2.html)** and edit the file with the next line (Change ***FOLDERNAME*** to the name you put to your DLC BASE Folder):

For "**dlclist.xml**": 

		<Item>dlcpacks:\FOLDERNAME\</Item>        

And now, save changes and put it back to directory mentioned in **Step :four:**.

**IMPORTANT: Edit "content.xml", and "setup2.xml", changing each "FOLDERNAME" word that you find in each file with the word you use as name for your Add-On's folder. Otherwise, your game will crash.**

**Now you have a BASE folder to put replace cars files and data inside as Add-On's.**

**Step :six::** Is the moment to put files into their respective directories. Rename "**car.ytf/.ytd**" files, for example "**chall.ytd/.ytf**" (Chall = Challenger), and put them into "`/FOLDERNAME/dlc.rpf/x64/vehicles.rpf`". Do the same process with "**car_mods.rpf**" files, but put them into ""`/FOLDERNAME/dlc.rpf/x64/vehiclemods`" (Don't forget to rename files inside "**car_mods.rpf**", otherwise, they'll conflict with the replacer car tuning parts).

**Step :seven::** Add **DATA** from replacer cars **(if the car you want to put as Add-On didn't have data when you downloaded it, take data from the original game car that it replaces)** to "**vehicles.meta", "carcols.meta", carvariations.meta**" and "**handling.meta**", which located in "`/FOLDERNAME/dlc.rpf/data/`" editing them with any text editor.

**Step :eight:** (SKIP this if your car doesn't have Tuning Parts): Once you did steps above, if some of the cars you added have **Tuning Parts** (car_mods.rpf), now go back to "`/FOLDERNAME/dlc.rpf/`",  export "**content.xml**" file, edit with **Notepad++** or any other editor and add these lines **to their respective section:**

For "**<dataFiles>**" section:

		<Item> 
	          <filename>dlc_FOLDERNAME:/%PLATFORM%/vehiclemods/car_mods.rpf</filename> 
	          <fileType>RPF_FILE</fileType> 
	          <locked value="true"/>
	          <disabled value="true"/>
	          <persistent value="true"/>
	          <overlay value="true"/>
	        </Item>

For "**<filesToEnable>**" section:

		<Item>dlc_FOLDERNAME:/%PLATFORM%/vehiclemods/car_mods.rpf</Item>        

***Finally, if you did all correctly, you can try your new Add-On cars ;)***

**___________________________________________________________________________________________________________________________________________________________________________**

| `Tutorial`: **ADD-ON** to **REPLACER** Vehicles
|:-:|

**`BEFORE YOU START:`** If it's the first time you will do a replace vehicles folder, follow all the steps below. When you complete that, verify that your replace vehicle is working fine before you add more vehicles into it.

**There will be an already made replace folder in the final of this section, in case that you want to compare your results with my own folder.**

**Step :one::** First, you need to download your desired file, for example, let's take the [**Ford GT 2005** by **Aige**](https://es.gta5-mods.com/vehicles/2005-ford-gt-aige).

**Step :two::**  Once you have the mod downloaded, unzip and open "**dlc.rpf**" file with **OpenIV**.

**Step :three::** Find the "**fgt.ytd**", "**fgt.ytf**" and "**fgt_hi.ytf**" files using **Ctrl + F3** and **export** these files anywhere you want. Do the same but with "**fgt_mods.rpf**" file. (**Don't close "dlc.rpf" file opened with OpenIV yet, because we'll take the metadata information for Tuning Parts later on**).

**Step :four::** Rename the exported "**fgt.ytd**", "**fgt.ytf**", "**fgt_hi.ytf**" and "**fgt_mods.rpf**" files to "**bullet.ytd**", "**bullet.ytf**", "**bullet_hi.ytf**" and "**bullet_mods.rpf**" respectively. These are the files that will replace the BULLET game vehicle and its tuning with the Ford GT 2005 models that you've downloaded previously.

**Step :five::** **[Download this file as a base for your Add-On's](https://es.gta5-mods.com/tools/add-on-replace-base-folder).**

**Step :six::** Once downloaded, unzip to anywhere you want.

**Step :seven::** Now, open **OpenIV**, go to "`/mods/update/x64/dlcpacks/`", create a **new folder** called as you want (I usually call my packs as "**A2NS**", "**A2NS2**", "**A2NS3**", etc) and put inside the "**dlc.rpf**" file of the **option #4**.

**Step :eight::** Go back to "`/mods/update/`". Now, go to "`/update.rpf/common/data/`" and export "**dlclist.xml**" to anywhere you want on your system.

**Step :nine::** Use a text editor as **[Notepad++](https://notepad-plus-plus.org/download/v6.9.2.html)** and edit the file with the next line (Change ***FOLDERNAME*** to the name you put to your new folder):

For "**dlclist.xml**": 

		<Item>dlcpacks:\FOLDERNAME\</Item>        

And now, save changes and put it back to the directory mentioned in **Step :seven:**.

**IMPORTANT: Edit "content.xml", and "setup2.xml", changing each "FOLDERNAME" word that you find in each file with the word you use as name for your Add-On's folder. Otherwise your game will crash.**

**Now you have a BASE folder to put replace cars files and data inside as Add-On's, but they will still replace the game vehicles that's the best part of this process.**

**Step :keycap_ten::** Is the moment to put the files into their respective directories. Put the exported vehicle files (the "**bullet.ytd**", "**bullet.ytf**" and "**bullet_hi.ytf**" files) into "`/FOLDERNAME/dlc.rpf/x64/vehicles.rpf`" (Remember that "FOLDERNAME" is the name of your folder!). Do the same process with the "**bullet_mods.rpf**" file, but put it into ""`/FOLDERNAME/dlc.rpf/x64/vehiclemods`".

**Step :one::one::** Add the metadata information from the new car to the "**carcols.meta**" and "**carvariations.meta**" files respectively, which are located in "`/FOLDERNAME/dlc.rpf/data/`" editing them with any text editor (This path is supposed to be the place where the metadata files (.meta) of your replace folder should be).

**`WARNING:`** The "**vehicles.meta**" and "**handling.meta**" files won't work there. These files should be edited on the following path:

- Path for "**handling.meta**" file: "**`mods/update/update.rpf/common/data/`**"
- Path for "**vehicles.meta**" file: "**`mods/update/update.rpf/common/data/levels/gta5/`**"

**Step :one::two::** Now it's the time to edit the previous metadata information files. Do this process for all of them (except "**handling.meta**" and "**vehicles.meta**" files, which should be edited in a different way):

- **Open** the file and search for the word "**fgt**". You should find, at least, one result or more depending on which file you're editing.
- **Replace** the found word/s with "**bullet**" until there's not any "**fgt**" word left.
- **Save** the changes and do the same process for every metadata file.

For the **handling.meta** and **vehicles.meta** files, instead of renaming we will do the following:

- Export both files anywhere you want. Open them and find the "**bullet**" lines.
- From the first "**<item>**" to the first "**</item>**" open/close tags of the "bullet" find, replace the content with the same lines provided by the Add-On file that you've downloaded, but remember to keep the name "**bullet**".

Once it's done, import them again to the respective paths.

**Step :one::three::** Once you did steps above, now go back to "`/FOLDERNAME/dlc.rpf/`",  export "**content.xml**" file, edit with **Notepad++** or any other editor and add these lines **to their respective section:**

For "**<dataFiles>**" section:

		<Item> 
	          <filename>dlc_FOLDERNAME:/%PLATFORM%/vehiclemods/bullet_mods.rpf</filename> 
	          <fileType>RPF_FILE</fileType> 
	          <locked value="true"/>
	          <disabled value="true"/>
	          <persistent value="true"/>
	          <overlay value="true"/>
	        </Item>

For "**<filesToEnable>**" section:

		<Item>dlc_FOLDERNAME:/%PLATFORM%/vehiclemods/bullet_mods.rpf</Item>        

***Finally, if you did all correctly, you can try your new Add-On cars working as replacers without having to mess with most of the original game files ;)***

| **[DOWNLOAD THE EXAMPLE MADE BY ME HERE](https://drive.google.com/file/d/1DHHplSXWqESRtFFNp3Zk5A1xRPQzeBRs/view?usp=sharing)**
|:-:|
**___________________________________________________________________________________________________________________________________________________________________________**

| `Tutorial`: **REPLACER** to **ADD-ON** MELEE Weapons
|:-:|

| :anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger: WARNING :anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger:
|:-:|
Never tried to put weapons as Add-On's, so if something does not work correctly with yours, remember that these steps are only for MELEE weapons, and maybe won't work for other weapons type. If you have any doubt about this method, please ask to @yeahhmonkey, he was who got it working, I only helped a bit in the process.
| **:anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger::anger:**
|:-:|

Before you start with steps, I recommend use **[this method to follow the process](https://es.gta5-mods.com/weapons/add-on-melee-weapon-base)**, otherwise this method could not work for you.

**STEPS:**

**Step :one::** First, you need to download your desired MELEE weapon file.

**Step :two::**  Once you have the mod downloaded, unzip and take "weapon.ytd/.ytf" files. Open OpenIV and go to "`/dlc.rpf/x64/models/cdimages/weapons.rpf`" and put these files there.

**Step :three::** Go to "`/dlc.rpf/common/data`" and add **DATA** from the **Replacer weapon** (take it from original Rockstar Game files or if weapon comes with his own, use it) to each file of this location, and don't forget to do the same if needed with **"/ai"** and **"anim"** folders inside the previous one, but mainly they shouldn't be edited. 

(Don't forget to replace "**FOLDER**" word in all the files that have it with the name of your DLC folder.) (**Be sure you're doing all correctly, please, be careful with this step**).

**Step :four::** Now go to "**/dlc.rpf/**", edit "**content.xml**" and "**setup2.xml**" files and change each "**FOLDER**" word with the name of your new DLC folder (if you changed it, obviously, otherwise don't do that).

**Step :five::** Use a text editor as **[Notepad++](https://notepad-plus-plus.org/download)**, edit "**dlclist.xml**" file in "`/mods/update/update.rpf/common/data`" with this line (Change **FOLDER** to name you put to your DLC BASE Folder):

For "**dlclist.xml**": 

		<Item>dlcpacks:\FOLDER\</Item>

**___________________________________________________________________________________________________________________________________________________________________________**

| `Tutorial`: ADD-ON to REPLACE - MELEE Weapons
|:-:|

This method is very simple and you have 2 ways to do it, just use ONE of the below (I really recommend the FIRST WAY, is the easiest and fastest one):
-

**FIRST WAY (Highly Recommended):**

**Step :one::** Change all "weapon.ytd/.ytf" name files to an existing one. For example, if you have an knife called "knifeADD" and you want it as replacer for the original "Knife" of the game, just change his ".ytd/.ytf" names to "Knife.ytd/.ytf", and it will appear as replacer. 

**Step :two::** Taking the example above, open every DATA file of the Add-On, and change any "knifeADD" name found into them with the "knife" word. This will make that "knifeADD" data now will work for "knife" weapon.

**SECOND WAY (Much more stressfull. Only for people with a lot of free time and patience):**

**Step :one::** Rename **"knifeADD"** (taking the First Way EXAMPLE) weapon files located in "`/dlc.rpf/x64/models/cdimages/weapons.rpf`" to **"knife"** and place them to the **"knife" original game location files** (Use Ctrl + F3 with OpenIV to find them).

**Step :two: (Stressfull):** Change all **"knifeADD"** words inside each DATA file to **"knife"**. Then copy/paste every DATA lines from every DATA file to his respective file located in any of the **"patchdayXng"**, replacing old lines.

--------------------------------------------------------------------------------------------------------------

**You finished!!** :grinning:

--------------------------------------------------------------------------------------------------------------

| `POLL`: ¿How can I improve this tutorial?
|:-:|

**You're free to help me improve this tutorial or help others, as @yeahhmonkey and more awesome people did already ;).**

**I want to convert this tutorial as a base/resource for GTA V modding, so, if you have more information about other GTA V errors, please provide it to me or add a comment here, so I can read and add it to this Tutorial.**

To make it easier, just copy/paste and replace the following lines of code with the specific information on each part:

    - **`ERROR NAME HERE`:** Definition about why it happens here (If you have no idea, write VOID). 
    ***How to fix that?*** Here your explanation about how to fix it (If you have no idea, write VOID).

**___________________________________________________________________________________________________________________________________________________________________________**

***`If I missed something or you're having problems using this method, please leave a comment.`***