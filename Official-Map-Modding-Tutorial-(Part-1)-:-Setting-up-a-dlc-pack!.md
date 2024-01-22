**Background Info:**
Hello, my name is Skylumz, I have been making map mods for about 3 months now and have learned alot within that time. I get a lot of questions on map modding, so I decided to make this tutorial to refer anyone to. I also want more people to get into GTA V map modding.  Anyways, hope you enjoy the tutorial and if I didn't address anything please comment below. This tutorial is not for beginners, you need to know how to download and install DLC packs , script mods, and navigate OpenIV.

**Things I will be covering:** 

* Completely setting up a DLC pack for map modding.
* Taking a model and converting it to *.ydr from scratch, with embedded collisions and textures.
* Explaining all file types that have to do with map modding (*.ymap, *.ytyp, *.ymf, etc)
* Spawning the custom .ydr that you made with a GIMS EVO

**Programs we will be using:**

* Blender (or your preferred modeling program) https://www.blender.org/download/
* Codewalker https://www.gta5-mods.com/tools/codewalker-gtav-interactive-3d-map
* Gims EVO https://www.gta5-mods.com/tools/gims-evo-with-gta-v-support
* 3DS Max https://www.autodesk.com/education/free-software/3ds-max
* Create YTYP Generator https://www.gta5-mods.com/tools/ytyp-generator-using-odrs
* Open IV https://www.gta5-mods.com/tools/openiv


**Explaining the file types:**

* **RPF:** This file contains all file types that GTA V uses. The most important thing to know about this file is that it contains all your map mods content.

* **YMAP:** The .ymap contains a bunch of information related to a entity. Like its coordinates, and more but the most important thing to know is that the .ymap will define where the object is placed in GTA V's world.
* **YTYP:** The .ytyp contains a list of entity's depending on how many are specified in it, that tells GTA V what textures to define a entity, and if the collision is embedded in the entity, etc. Now the most important thing to know is the file defines all info regarding a specific entity that could be spawned.
* **YMF:** This file enables .ymap files inside a .rpf. The most important thing to know is that .ymaps will not work without this.
* **YDR:** This file contains all information regarding a single drawable(entity), like the objects textures(if embedded), and the LODs. It can only contain a  max of 4 LODs. The most important thing to know about this file is that it contains everything regarding a specific drawable.
* **YDD:** This file is the basically a bunch of .ydrs into one. It is a drawbable dictionary. The most important thing to know is that it is a bunch of .ydrs crammed into one file.
* **YFT:** This file has a drawable in it most likely a vehicle. I dont know much about it as of now.
* **YBN:** This file contains bounds information, aka collision. The most important thing to know about this file is that it is for collision.
* **YTD:** This is a texture dictionary. It basically contains a bunch of textures that a .ydr can access. The most important thing to know about this file is that if a .ydr doesnt contain the textures embedded then it most likely uses this to access textures.

Now that I have explained the file types, you can always look back and look through them if you don't understand one. I hope I explained them well enough.



**Setting up a DLC pack for map modding:**

**Step One**: Open OpenIV and locate your dlcpacks folder should be : *YourGTADirectory*\mods\update\x64\dlcpacks

**Step Two**: Go into edit mode and create a new folder, this folder will be the DLC's name so make it something meaningful towards the specific map mod. For now I will be using **EXAMPLEDLC** for this tutorial. Should look something like this: 
![0_1517983252576_upload-1b4846f6-8d09-4c02-be03-d807af214dd9](https://images.gta5-mods.com/uploads/c94d2d19-fc79-4a8f-bc1d-ea56bbd091b1)

**Step Three**: Double click the folder you just created and click *Ctrl + N* to create a new .rpf archive. You can also right click > new > RPF Archive (.rpf version 7). Both ways work choose, what suits you. Next you will see a dialog popup asking for the .rpf name it absolutley has to be **dlc.rpf**. Like this: 
![0_1518008549901_upload-5f250327-31bd-4ed7-ac65-8c314a3e39a1](https://images.gta5-mods.com/uploads/a03a6ea5-dce1-4aae-97fb-ec2f74dfc420) 
Once finished:
![0_1518008580047_upload-aeb9f128-18cf-4759-9a9c-8067b8a077a4](https://images.gta5-mods.com/uploads/a9347094-d89a-4901-97b5-92ba4e771994) 
Go inside that dlc.rpf you just created and you are gonna want to make a folder named x64 you can do this with *Ctrl + D* or Right Click > New > Folder or Clicking this icon:![0_1518008737230_upload-e96cb0de-1818-46b7-b39c-be7f42586594](https://images.gta5-mods.com/uploads/7b0268e2-61e4-4d7a-92ff-010b6a8d8bbf) Now go inside of the x64 folder you just created and make another folder named *Levels* and inside that another folder named *gta5* inside of that create another .rpf and name it anything you want, for my own naming strategy I usually name it what it has to do with that portion of the mod but for this example we can just name it *models.rpf*. Anyways by the time you are done this should be the DLC packs structure:
![0_1518010031641_upload-3ef2467a-88dd-49dc-8be0-00af1dcb1652](https://images.gta5-mods.com/uploads/6dda02b4-4042-4c6e-9e79-36e5954e8753) 

**Step Four**: Now its time to add the content.xml and the setup2.xml. You can download the example ones from here : **https://ufile.io/20v3b** you will get a content.xml and setup2.xml all you need to do is place both of them inside the dlc.rpf (beside the x64 folder) like this: 
![0_1518010532347_upload-84be5902-1af4-4233-b70d-e9f63f02d051](https://images.gta5-mods.com/uploads/28457389-9f44-48cc-ad18-d18b8c098a29) 
Then Right Click the content.xml while in edit mode and click *edit* and go to the search tab and search "DLCEXAMPLE" now replace every single one the words that say "DLCEXAMPLE" and "YOURDLCPACKNAME"with whatever you named the dlc pack in step two. For example : 
![0_1518011048435_upload-e0ab0ea8-656a-4a7e-a667-6a76003e2d2b](https://images.gta5-mods.com/uploads/4703aaab-c82b-4849-9f53-7c7e7f2d7cd6) 
Now once you have replaced all them lines you can open up the setup2.xml and do the same. For example:
![0_1518011211018_upload-679b1004-bc58-4228-b42f-5c83c48e782d](https://images.gta5-mods.com/uploads/79f70b96-9ca3-4106-bd86-35295bcc779c) 
There are more than that so be sure to replace ALL "DLCEXAMPLE" with your dlc pack name choosen in step two.

**Conclusion**: You have just finished making your first map modding dlc pack. If you plan on making dlc packs alot then get used to making this pack its fairly simple. 

**Extra notes**: 

* if you named the models.rpf something else you need to replace that in the content.xml for example if you named it "props.rpf" you would have to change these lines:![0_1518011524050_upload-732977d7-205f-4877-ae5e-a68f92bc6461](https://images.gta5-mods.com/uploads/c244d2be-147c-48ef-b76c-89fbf19bfaaa) 
* I will go into more detail but when you add in .ytyps then you have to enable them in the content.xml just like the .rpf file. I will explain alot better but for example: 
![0_1518011664732_upload-74a18837-b748-4251-8f0c-35c9147ca18c](https://images.gta5-mods.com/uploads/67e1874a-41cf-49a9-8569-fc500f1e3d4f) 
* I made a quick example of how all these files work together which you can view here: 
![0_1518011975095_upload-e45fee40-4965-435b-84dd-01dabee80a4f](https://images.gta5-mods.com/uploads/a611de2d-e3ca-421b-86b4-d5b91acab1d0) 
* I wanted to explain how dlc packs work so if you run into problems you can change them manually. If you want to skip making the content.xml and setup2.xml then use this program I made: **https://www.gta5-mods.com/tools/dlc-meta-generator-content-xml-and-setup2-xml** Read the instructions on how to use!

**IF YOU NEED HELP BEST WAY TO CONTACT ME IS THROUGH DISCORD YOU CAN JOIN MY MAP MODDING SERVER HERE : **https://discord.gg/7xbYQaN** Your always welcome dont be afraid to join!!**

**PART 2:** https://forums.gta5-mods.com/topic/17815/official-map-modding-tutorial-part-2-making-a-custom-ydr