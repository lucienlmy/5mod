**Background Info:**
Whats up modders back at you with my second tutorial for gta V map modding. In this one we will be making a custom .ydr. The next tutorial will show you how to add it in gta V. 

**REMEMBER TO CHECK OUT MY PREVIOUS TUTORIALS BEFORE DOING THIS ONE**

* Part one: https://forums.gta5-mods.com/topic/17754/official-map-modding-tutorial-part-1-setting-up-a-dlc-pack

**Programs we will be using for this tutorial:**

* Blender (or your preferred modeling program) https://www.blender.org/download/
* Gims EVO https://www.gta5-mods.com/tools/gims-evo-with-gta-v-support
* 3DS Max https://www.autodesk.com/education/free-software/3ds-max
* Open IV https://www.gta5-mods.com/tools/openiv

**Making a custom .ydr**

For this tutorial we will be converting a cube model into .ydr because I want to start out with something simple. For more complex objects its more or less of the same. I will be showing you how to make it from blender, you can use your preferred modeling software. Anyways lets get started.

**Step One**: I will be making a cube in blender, I wont be explaining how to make the cube, but I will be going over a couple things when converting from blender. First thing is whatever you want to be textured make sure it has a specific material assigned. For example, for this cube I have assigned a material named "Cube Texture" now I will be making this a solid color, but for more complex objects you will need to uv map, texture, etc. Like this:
![0_1518012705320_upload-f4380b7b-11aa-4069-9795-5b03ac2f25e4](https://images.gta5-mods.com/uploads/08cecadb-5c4b-4e5a-a695-0f998bff616f) 
I would also usually use a ped or vehicle to judge the scale but for this simple object I am just gonna make the size 0.01. Now I will export as .fbx and have it where I can access it.

**Step Two**: Open up 3ds max you must have installed and setup gims evo for this step. The first thing to do is import the .fbx you made earlier. Now once viewing the .fbx make sure the scale factor is set to 1.0 for example:
![0_1518012952316_upload-7ae5c0a4-668c-444e-8c42-73a0a8c736d9](https://images.gta5-mods.com/uploads/cbf718c5-297a-4e6e-b7ca-7651d8f2303f) 

**Step Three**: Once inside gims evo you will want to click the object hierarchy on the right side and reset the transform and scale for example:
![0_1518013042431_upload-cf9c37fd-2cc0-4571-9b5e-5e88d7d032fd](https://images.gta5-mods.com/uploads/34e52eca-703c-4d83-8a2d-8be0ad5e4d5d) 

**Step Four**: Now what you wanna do is right click the object and clone it make sure to clone it as a copy and not a instance. This cloned object will be for your embedded collision so I would name it the "Objects name"  + _col for example:
![0_1518013305666_upload-2ea378f1-c900-405d-a0f1-6e3e0d272e3c](https://images.gta5-mods.com/uploads/84da1769-21e9-4bcd-9ff0-06e8397ceeeb) 

**Step Five**: Now you want to make the collision material to do this just click the material editor:
![0_1518013595339_upload-190c1fbb-5f7c-4d61-bbef-185a75eb4127](https://images.gta5-mods.com/uploads/964a9cd7-5ec5-40b7-aa9b-8a757f2109bb) 
Now once in the material editor you will want to click the shader type:
![0_1518013688208_upload-6af8a4bf-2ddd-40af-836a-b22254100dfd](https://images.gta5-mods.com/uploads/849498e7-d173-431d-8643-f05bb15f6325) 
Like so, then select GIMS V Material for example:
![0_1518013729032_upload-22282783-fd90-4c4c-b6a1-fe95743799f2](https://images.gta5-mods.com/uploads/b6e8691a-6367-423d-9f60-e09d6e12a937) 
Next, you wanna select the group and material type. For this example I want the cube to be like concrete: 
![0_1518013922907_upload-69b3fd73-b800-4ca3-8d8c-b45a4226fc24](https://images.gta5-mods.com/uploads/a4594d8e-ba6b-4131-bc58-cdf7ed9c624d) 
Next, you wanna select the collision object and click apply material to selected object like so:
![0_1518014132377_upload-836dd215-5923-49db-80fb-03fa6d55c29e](https://images.gta5-mods.com/uploads/b6ce854d-c4b4-424f-9270-c1358c1b30f6) 
Making the collision material is done.

**Step Six**: To start, click "Create Object > Collisions > Composite" then click the scene view like this:
![0_1519785917679_upload-9ad114ad-4173-4250-82d0-a6a703333d9c](https://images.gta5-mods.com/uploads/eb567f71-da61-4625-b0cf-f67abb1c2f55) 
You will see the modifier pop and all you need to do is change the name to col for collision for example:
![0_1518014453779_upload-5d2bb237-7d31-43ec-8096-70a03ea73e23](https://images.gta5-mods.com/uploads/f4beabba-d094-4ba3-8dc2-aee820628a6a) 
Next, you wanna select the collision object and add a mesh:modifier to the collision object "Create Object > Collisions > Composite > Mesh:modified", like this:
![0_1519785968101_upload-96c456a1-0b45-470d-a027-13bb3c779008](https://images.gta5-mods.com/uploads/f74ed3fb-c87e-4418-9629-59f46af12d5b) 
You will see a new modifier be added to the collision object and this is how you need to set it up: 
![0_1518014627699_upload-8a68201f-275b-4797-a028-800dce20cc63](https://images.gta5-mods.com/uploads/0a1e4955-8e2d-496d-97f3-a9eaec9c0be6) 
Last thing to do is set the object collision under the collision composite. To do this you want to click the schematic view button:
![0_1518014777388_upload-fc141093-f7cf-404d-8216-eb282af9ff31](https://images.gta5-mods.com/uploads/49f7e64a-2210-4408-9d67-3674c47d05ce) 
Next, you want to grab the purple block that has the "objects name" + _col and click the link button then link it to the green col composite. Like this: 
![0_1518014877858_upload-7eb0b236-78ca-4129-897f-1d23d9c1518c](https://images.gta5-mods.com/uploads/272c9ffb-acc6-4e7e-b95a-e64a9074332e) 
If you have done this exactly as shown you will have done embedded collision correctly. Remember a object with more than 32k polys can not have embedded collision unless split into multiple objects. 

**Step Seven**: Making the model and game mesh modifier. To do this go to  "Create Object > Models > Model " then click on the scene view. Next name that object to the name that you want the actual model to be. For this cube I will name it "CubeExample". For example:
![0_1518035266460_upload-f75acc41-ac8b-49f2-81c1-d9cb5e59b9d2](https://images.gta5-mods.com/uploads/f6a7c096-f00b-406d-8d0a-926e38a361c3) 
Next, you need to click on the object mesh and go to  " Create Object > Models > Game mesh : Modifier" and then leave it as is, for example:
![0_1518035344975_upload-4f3625cb-10c4-4543-a2c5-667c5df334cc](https://images.gta5-mods.com/uploads/14c43401-cd2d-4226-b30a-4233701fa22a) 
 Now that's over you are almost done. You need to go back to the schematic view and make the object mesh and the col composite a child of the model in this case "CubeExample". Like so:
![0_1518035496369_upload-46723287-2d1d-43db-84f2-dbceee767b9b](https://images.gta5-mods.com/uploads/2154d40b-9502-478b-965e-0780d1d1331d) 

**Step Eight**:  Setting embedded texture. For this all I am gonna do is take a small .dds image that is the color I want the cube to be green in my case and you select the object mesh then click material editor. Like this: 
![0_1518035971045_upload-d785482a-0981-4b24-98a9-4e5cdf14c4e8](https://images.gta5-mods.com/uploads/b6c11cdb-4f0a-4772-86ff-07e38ebba74b) 
Now all you have to do is click the material and click options a dialog will pop up asking to convert to gtaV material click yes. For example:
![0_1518036042860_upload-feb4bef8-2fbe-4c20-889d-5675a320131b](https://images.gta5-mods.com/uploads/a9fdbafc-972f-409b-9414-d60ef261cf9b) 
Now a new dialog will pop up with all the material options for a simple embedded texture all we need to do as of now is click the embedded checkbox to true and select the diffuse texture and find the texture we want to apply to this material. Like this:
 ![0_1518036277717_upload-e89bea32-3e87-4c9f-919e-7402c695135b](https://images.gta5-mods.com/uploads/59abdf58-fdb5-47ca-99fa-879758c859a7) 
That is all you have to do for embedded textures. 

**Step Nine**: Now everything is complete last steps are to export the .odr. When exporting the hierarchy, absolutely has to be setup like this:
 ![0_1518037094702_upload-7705e95b-27f6-47f4-9122-b9ac4d0e1407](https://images.gta5-mods.com/uploads/d5817ea0-bbc7-45b0-9369-6fe523a32199) 

**Conclusion**: If you followed all the steps then you have successfully created your first custom .ydr with embedded collision and textures. Last thing for you to do is go to the models.rpf that's in your dlc pack from the last tutorial and import the .odr into openIV. Now when you double click it you should end up with something like this: 
![0_1518043759587_upload-5c22a7dd-ad46-4975-8dca-5cb155c7de57](https://images.gta5-mods.com/uploads/bc5733a6-97f8-4f94-a382-6a3488ae1acd) 
You can also view the edges and vertices by enabling the options to true:
![0_1518043881118_upload-13a22d15-d0c6-4bb0-a0f2-f2e749516b59](https://images.gta5-mods.com/uploads/869088ef-1c2e-4de8-a56b-a432683def10) 
To view the embedded collision just click "bounds" at the top:
![0_1518043942186_upload-726273a8-7ecf-42ad-8691-6c28d3edd441](https://images.gta5-mods.com/uploads/7d4789e4-53fc-4acf-9e61-e506b10533ef) 
You can also view the embedded textures by clicking "view embedded textures" at the bottom right corner:
![0_1518043996825_upload-5d9fb258-2b81-48d1-b538-6718cef6787e](https://images.gta5-mods.com/uploads/bd3ab777-85fe-4b4a-be64-9cc18e0bcfc4) 

**Extra Notes**: More complex objects will require more work and there is a lot about shader's, vertex painting, etc that I didn't cover. Don't expect to make rockstar quality models by using this method. This was just to show you a very basic example. I have alot more to teach you which one day I might get into, but for now this should do... 

**IF YOU NEED HELP BEST WAY TO CONTACT ME IS THROUGH DISCORD YOU CAN JOIN MY MAP MODDING SERVER HERE : https://discord.gg/7xbYQaN Your always welcome dont be afraid to join!!**