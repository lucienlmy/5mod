**Background Info:**
Back again with part 3. This one will show you how to start making your own custom ymap and spawn the custom .ydr you created in part 2 with codewalker.

**REMEMBER TO CHECK OUT MY PREVIOUS TUTORIALS BEFORE DOING THIS ONE**

* Part one: https://forums.gta5-mods.com/topic/17754/official-map-modding-tutorial-part-1-setting-up-a-dlc-pack
* Part two: https://forums.gta5-mods.com/topic/17815/official-map-modding-tutorial-part-2-making-a-custom-ydr

**Programs we will be using for this tutorial:**

* Codewalker https://www.blender.org/download/
* Ytyp Generator https://www.gta5-mods.com/tools/gims-evo-with-gta-v-support
* Open IV https://www.gta5-mods.com/tools/openiv

**Making a custom map using the custom .ydr created**

**Step One**: The first step you want to create a .ytyp for the object. All you need for this is a program I made. You can read the instructions on how to make a .ytyp for an object. All you need to do is open the .odr (we will be using CubeExample.odr) and calculate BB's then Import them and change the flags to 32, make sure to check embedded collisions and then name the ytyp file to something meaning full. Here is the CubeExample done:
![0_1518044613763_upload-f7ffedbe-1bc5-4270-8854-783844871808](https://images.gta5-mods.com/uploads/4e8fade1-397c-41c3-a564-52d5c28981ac) 
Now click create and then your done. Take that ytyp file created and set it next to the .odr used to create the ytyp. The last thing you want to do is go to the content.xml under the dlc.rpf and add in these new lines:
![0_1518046591226_upload-a5881781-d2e0-4039-a18d-7ecae28efd52](https://images.gta5-mods.com/uploads/29f81330-7b9c-4c03-b73f-6a12d64f590c) 
Replace the name that is highligted with the name of the .ytyp that was generated.

**Step Two**: Next just put the .odr and the .ytyp in the "models.rpf" that was created when setting up a dlc pack for map modding. Like this:
![0_1518044799064_upload-8ab2e02b-dec2-4c10-89c6-3041ecd88c9d](https://images.gta5-mods.com/uploads/27671fa1-9b76-46de-8048-4d059a227d8f) 

**Step Three**: Next you need to download this _manifest.ymf from here: **https://ufile.io/9cn4e** Just place that inside the "models.rpf" next to the ytyp. should look like this: 

![0_1518045022529_upload-db4e6067-40e9-414a-9993-719c5a4a394f](https://images.gta5-mods.com/uploads/a61f4806-9241-417d-8797-0d818321927c) 

**Step Four**:  Open codewalker you will see the gtaV world start to render. Next you need to click the little << in the corner and one by one enable mods and dlcs. Like so:
![0_1518045234990_upload-fc3b49f9-79a4-461d-94ed-0c8667d891f3](https://images.gta5-mods.com/uploads/0a439f04-81e0-4563-a97a-7afbf43bdaf6) 

**Step Five**: Now just click tools... and select project window then you will see a new window popup it should look like this:
![0_1518045299552_upload-dd6e936a-ff7f-4a4b-86e4-76674405f6e2](https://images.gta5-mods.com/uploads/cfddf712-0a21-4d74-b826-df7575b99017) 

**Step Six**: Now click file >new > ymap file and you will see this load:
![0_1518045412570_upload-08415fcc-4740-4e6f-b584-e5c466bdf4c0](https://images.gta5-mods.com/uploads/e1a78897-f65c-4afc-be77-87948f84671b) 
Now just select the map1.ymap and in the toolbar click ymap > new entity it should then show this:
![0_1518045543463_upload-9479ecd9-41aa-4a7f-b80b-460a43dc4bef](https://images.gta5-mods.com/uploads/6121373b-c8c2-4e99-94ad-d6eae69ab4e5) 
Now all you have to do is where it says "Archetype:" type in your custom ydrs name for this we will be using CubeExample **(MAKE SURE IT IS LOWERCASE)** Like so:
![0_1518045725526_upload-d8021015-7f2a-41de-af09-3624cf4c370a](https://images.gta5-mods.com/uploads/bd161d5c-213a-438d-b567-908b0e4f087c) 
Now you will see in the background your object loaded in. You can now move around to view it better. 
Now just click T and you will see a tool bar pop up: 
![0_1518046667067_upload-bab209e2-74ff-4bdc-bec3-972c97ad52dc](https://images.gta5-mods.com/uploads/22aad913-4d18-4303-90b6-98a0d683b6e2) 
Now you can move/rotate/scale the object with them buttons and place it where you want it in the world when you have it in a suitable location in the world click the map1.ymap and click "Calculate Extents". Like so:
![0_1518046724032_upload-d35d1f78-cec6-44a6-918a-892e53cc3880](https://images.gta5-mods.com/uploads/5d9f787b-fe2a-4460-9bc1-02de6a536f0f) 

**Step Seven**: Once that is done you can click file > save Map1.ymap as... And save it to a location where you will remember you can name it whatever you want for this tutorial I will use "cubeexample". Here is what it looks like done: 
![0_1518046767966_upload-f4fb7ead-3770-415f-a2c5-0bb85ddd412a](https://images.gta5-mods.com/uploads/7923b325-f5df-41cd-a536-a05c8f69261d) 
**Step Eight**:  After that click the "new codewalker project and the "manifset" tab and then click generate, you should get something like this:
![0_1518046813816_upload-793fbee1-4fa4-4053-8001-1a7e62ac8122](https://images.gta5-mods.com/uploads/3ccf84c5-ad63-4fc6-88f5-a799d9b3245d) 
After that you want to copy all that stuff generated and go into openIV where the _manifest.ymf is and paste all that data in and save it. Once done it should look like this:
![0_1518046874383_upload-8e53f844-f38b-4822-a6d9-aec60bd2460f](https://images.gta5-mods.com/uploads/516d439d-df38-493f-91f7-00ce53af6395) 

**Step Nine**:  Place the .ymap inside the "models .rpf " and thats it. Once all complete the models.rpf sshould look like this: 
![0_1518047109383_upload-22b67d09-7400-4fb1-a1c7-ac4b80e7b487](https://images.gta5-mods.com/uploads/b49a1cef-9661-468c-bcf0-1fddfcd3e32e) 

**Conclusion**: Time to test. I placed the cube right in front of franklins house so I could see it really quick, here is a screenshot:
![0_1521026661232_upload-0d7d7f1f-336f-46e5-b634-8f4a225ffa9b](https://images.gta5-mods.com/uploads/9410b4d3-b32b-4c3f-af67-402fbfe47e8c) 
**Extra Notes**: Never forget your _manifest.ymf or the ymap will not be loaded. 

**IF YOU NEED HELP BEST WAY TO CONTACT ME IS THROUGH DISCORD YOU CAN JOIN MY MAP MODDING SERVER HERE : https://discord.gg/7xbYQaN Your always welcome dont be afraid to join!!**