Hi today i show u how create a custom sprite to render it on screen.

**Requirements**
- ScriptHookV
- openIV.asi (install from openIV software)
- backup original game files (**/update/update.rpf**)

**Let's start**
Copy file from **/update/update.rpf** to **/mods/update/update.rpf**
Run openIV software and open file 
**/mods/update/update.rpf/x64/textures/scripts_txds.rpf**
![alt text](http://i.imgur.com/MUfVJqX.png)
Then **Right click>New>Texture dictionary** (I named it **customTexture**).
![alt text](http://i.imgur.com/ufpQVB2.png)
Open **customTexture.ytd**.
Click **Import button**(**1**).
In new window select your texture (.png/.jpg) (**2**) and click **Open** (**3**).
Dont forget click **Save** (**4**).
![alt text](http://i.imgur.com/tptkzwx.png)
Done.

To draw sprite:
**UISprite sprite = new UISprite("customTexture", "textureName(without extension)", new Size(100, 100), new Point(100, 100));
//in Tick
sprite.Draw();**

I think that helped.

Greeings for @LeeC2202 for help.