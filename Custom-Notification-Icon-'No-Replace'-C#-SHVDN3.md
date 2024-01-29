New file path in v1.58 (Icons) 
New= mods\update\update.rpf\x64\textures\script_txds.rpf\
Old= mods/x64b.rpf/data/cdimages/scaleform_generic.rpf

Hello everyone,
Here is a quick tutorial on **"How to add and use custom notification icon"** *in C# / SHVDN3*
Without any original game file replacement ! You also could use **the first part of the tutorial** & use a **different notifications way** with custom icons
So to start, you will need **OpenIV**, and a **picture in size 64x64** *(Pixels)* **in .dds type**
You could use any software to create this picture or download it & convert.
I'm using GIMP, which allow exporting/converting in .dds *(& is free !)*

![Preview](https://i.ibb.co/rZ7sX1F/CShop.png) 
Each notifications have 3 fields, 
*  Subject, Who or what send the message (Here = City Car Shop)
*  Object, what type of message or what message is about (Here = Information : )
* Message, obviously what it says ! (Here = Welcome to the Shop)

When you have your **picture** *(in .dds)*, you will have to **put it in game file**.
Here the picture will be called **"Icon01"**
Open **OpenIV** & allow **edit**
Go to **mods\update\update.rpf\x64\patch\data\cdimages\scaleform_generic.rpf** *(If needed dump original files to mods folder)*
Then open **New** *(Top left)*, & click **textures dictionary** *(.ytd)*
Enter the texture dictionary name you wants, here we will take **"TextureDict01"**, then click **OK**
Now, **find it & open it**.
Then **import your pictures** *(Top left)* in .dds format
& then **SAVE !**

Now the most interesting part, **the code !**
 **Create a Method in ModName : Scripts**
```cs
void notifyAboveMap(string msgtype, string msg)
        {
            Function.Call(Hash.BEGIN_TEXT_COMMAND_THEFEED_POST, "STRING");
            Function.Call(Hash.ADD_TEXT_COMPONENT_SUBSTRING_PLAYER_NAME, msg);
            Function.Call(Hash.REQUEST_​STREAMED_​TEXTURE_​DICT, "TextureDict01", true); //Here you put the texture dictionary name you choose before
            Function.Call(Hash.END_​TEXT_​COMMAND_​THEFEED_​POST_​MESSAGETEXT, "TextureDict01", "Icon01", false, 1, "Turf Weapons & Armor Stock", msgtype); //the 5th argument here is Subject/Biggest top title, see picture
        }
```
Now we have our method, lets call it in your scripts,
```cs
notifyAboveMap("~g~Information ~w~:, "~b~Welcome ~y~to ~w~the ~g~Shop") // here you put Object first & Message then
```
Then **it should work** !