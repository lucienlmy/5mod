Hello everyone,
Here is a complete tutorial on **"How to create your own Help notifications with Key bind or Blips"** *in C# / SHVDN3*
It show **different key bind depending on what you are using & actually game state** or *(moving)* Blips, Street, & more !
I also added **7 different context of use** for each **7 possibility**, and so **7 example of use !** 
So depending on your actual knowledge you may **learn a lot more then only Help Notifications !**
It may be considered as **code snippets**, I tried to put **as much knowledge as possible**, *I hope it's not too much !*
KeyBoard =
![KeyBoard](https://i.ibb.co/XXb17Dc/PressE.png)
Controller = 
![Controller](https://i.ibb.co/fMc0Phj/Press-Left.png)

Each Notifications could show **Blips, Key, Player/Ped & More !**, Text may be **Bold or Colored & More !** 
*(Full list = https://pastebin.com/nqNYWMSB)*

**Care not Tested** , AFAIK If you want to use **moving Blips,** or **anything that requires constant update** *(Moving, or alive, & more)* You **could only use** Easiest Way - Normal Way:2nd - Natives&Hard Way:2nd 
Precising those Informations will be appreciated !

Both line **#region & #endregion aren't used by the code**, they are only **useful for us coder**, Here is an exemple of use, 
***
# Summary  
It's almost always from easiest to hardest ! 
* Easiest Way (Exemples: Display when the **game & scripts** are **fully loaded !**)
* Normal Way 
  * **1st :** Show Help **ONE/EACH tick**. > **Exemple Context :** Dipslay when **Player position is next to Shop position** 
  * **2nd :** Show Help **until its turned off by Same** line > **Exemple Context :** Display when User press Key, With anti-Spam Security**bolded text**
  * **3rd :** Show Help **until it's turned off** by different line > **Exemple Context :** Display when User press Key, With Closing Timer
* Hardest & Natives Way 
  * **1st :** Show Help **ONE/EACH tick** > **Exemple Context :** In cover, Health refill, with cost and display ! 
  * **2nd :** Show Help **until its turned off by Same** line > **Exemple Context :** Simple random Dice Game, with Smart display !
  * **3rd :** Show Help **until it's turned off** by different line > **Exemple Context :** Press F Joke, When player reach 90km/h = 25 M/s
***
# **Easiest way** *(Thanks to @JohnFromGWN)* **=**
In your scripts you just have to **call EACH Tick this function** :
### **Essential scripts** with no exemples or context :
```cs 
GTA.UI.Screen.ShowHelpTextThisFrame("~b~Press ~INPUT_CONTEXT~ ~w~to ~y~Open ~b~Car ~g~Shop");//Here you put the text you want between " "
```
**To end** obviously **stop calling the function** ;)

### **Exemple Context :** Display when the **game & scripts** are **fully loaded !**
Here it will wait until **game is loaded** to just **display help notification**, then it will be **closed** by **user pressing the key**
```cs
public class ModName : Script
{
    public ModName()
    { 
        //...Your Method/Function...
        Tick += onTick;
    }
    void onTick(object sender, EventArgs e)
    {
         //...Your Method/Function...
         bool textSeen = false;  //This will be used to stop "Help" display
         if (Game.IsLoading == false && textSeen == false)     //Check loading state , & if text as been closed
         {
             GTA.UI.Screen.ShowHelpTextThisFrame("~r~Game ~y~is ~g~Loaded ~w~! ~b~Press ~INPUT_CONTEXT~ ~w~to ~g~Close ");//Here you put the text you want between " "
         };          //Dont miss ";" after each if() {}; or if() {} else {};
         if (Game.IsControlJustPressed(GTA.Control.Context)) //If user press E or left then >
         { textSeen = true; }; //It put textSeen on true, so it stop display !, Take care of each ";"
    }
}
```

# **Normal Way** *(Thanks to @Jitnaught & @JustDancePC)* =
***
## **1st :** Show Help **ONE/EACH tick**
*(Need to call on each display tick so !)* 
[Arguments = Loop: false |Shape: 1 to 50]
### **Essential scripts** with no exemples or context :
```cs
GTA.UI.Screen.ShowHelpText("~b~Press ~INPUT_CONTEXT~ ~w~to ~y~Open ~b~Car ~g~Shop",1,true,false);//Here you put the text you want between " "
```
### **Exemple Context :** Dipslay when **Player position is next to Shop position** 
*Shop Position = x:-212 y:-1618 z:34*
It will display Help when **player position is next** / near **to Shop position**

```cs
public class ModName : Script
{
    public ModName()
    { 
        //...Your Method/Function...
        Tick += onTick;
    }
    void onTick(object sender, EventArgs e)
    {
         //...Your Method/Function...
         if (World.GetDistance(Game.Player.Character.Position, new Vector3(-212.4f, -1618f, 34.1f)) > 4f) //Distance Check 4f=4m radius around Vector3 Pos
         { 
             GTA.UI.Screen.ShowHelpText("~b~Press ~INPUT_CONTEXT~ ~w~to ~y~Open ~b~Car ~g~Shop",1,true,false);//Here you put the text you want between " "
         };          //Dont miss ";" after each if or if else
    }
}
```
With this exemple it will **stop displaying** when **player** will **move** from the RADIUS *(4m)* around **Vector3 location**
If you did any other way **To end** obviously **stop calling the function** ;) *(Here if(World.GetDistance...) increase it just automatically stop calling !)*
***
## **2nd :** Show Help **until its turned off by Same** line 
*(Is turned OFF is the game/scripts reload)* [Arguments = Loop: false |Shape: -1]
### **Essential scripts** with no exemples or context : 
```cs
GTA.UI.Screen.ShowHelpText("~b~Press ~INPUT_CONTEXT~ ~w~to ~y~Open ~b~Car ~g~Shop", -1,true,false); //Here you put the text you want between " "
``` 
### **Exemple Context :** Display when User press Key, With anti-Spam Security**bolded text**
Here, For exemple, we will **call** when **User press Input_Context**, The key showed on picture, Keyboard:**E** Controller:**Right** 
```cs
public class ModName : Script
{
    #region Initilization
    bool security = false;    //Here we initialize a security Boolean Value to false
    int timeCounter = -1; //Here using an init to -1 allow us to use this int from 0 to X without confusing with (Re)Initialization Value
    #endregion
    public ModName()
    { /*...Your Method/Function...*/ }
    #region OnTick
    void onTick(object sender, EventArgs e)          //You need to know one Tick +- = one ms
    {
        //...Your Method/Function...
        #region Control or Input
        if (Game.IsControlJustPressed(GTA.Control.Context) && Security == false)   //Here we get user input, and check security
        {
             GTA.UI.Screen.ShowHelpText("~b~Press ~INPUT_CONTEXT~ ~w~to ~y~Open ~b~Car ~g~Shop", -1,true,false); //Here you put the text you want between " "
            security = true; //Here, we activate security to avoid double input or lags (Only one key press each 1/5sec)
        };
        #endregion
        #region Security & Time Counter  
        if (security == true) 
        { 
             if (timeCounter < 0) { timeCounter = 200; };                  //Here it is start point, so it start the time counter, 200 is a time in ms, So 0.2 sec or 1/5 sec
             if (timeCounter > 0) { timeCounter--; };           //Here "--" is like timeCounter=timeCounter-1, So each ms it decrease -1
             if (timeCounter == 0) { timeCounter = -1; security = false; }; //Here, when a really small time have passed, It reinitialize to default : the timeCounter(=-1) & the secuity Lock(false)
        }; // ";" always after if(){}; or if(){}else{};
        #endregion
    }
    #endregion
}
```
**To clear the Help, User** just **press the key** again ! If you **did it another way,** just **call** the exact **same function again**.
***
## **3rd & harder :** Show Help **until it's turned off** by different line
*(Keep open even if the game/scripts reload)* 
[Arguments = Loop: true *(then false)* |Shape: 1 to 50]
### **Essential scripts** with no exemples or context :
```cs
Start:
GTA.UI.Screen.ShowHelpText("~b~Press ~INPUT_CONTEXT~ ~w~to ~y~Open ~b~Car ~g~Shop", 1,true,true);  //Here you put the text you want between " "
End:
GTA.UI.Screen.ShowHelpText("~b~Press ~INPUT_CONTEXT~ ~w~to ~y~Open ~b~Car ~g~Shop", 1,true,false);  //Same text, false instead of true
```
### **Exemple Context :** Display when User press Key, With Closing Timer

Here, It will **call** when **User press Input_Context**, The key showed on picture, Keyboard:**E** Controller:**Right** )
Then it will **close after 10 sec** *(Instead of Natives:1st exemples, We will use a derived timeCounter to **count time in sec instead of ms**(=basic tick))*
```cs
public class ModName : Script
{
    #region Initialization
    int timeReference = Game.GameTime + 1000;  //Initialization of time references, used to count in sec
    int secTimeCounter = -1;     //Here, initialization at -1 avoid confuse with the timer ends ! same as Natives:2nd exemples
    #endregion
    public ModName()
    { /*...Your Method/Function...*/ }
    #region OnTick
    void onTick(object sender, EventArgs e)          //You need to know one Tick +- = one ms
    {
        //...Your Method/Function...
        #region Control or Input
        if (Game.IsControlJustPressed(GTA.Control.Context))   //Here we get user input
        {
             GTA.UI.Screen.ShowHelpText("~b~Press ~INPUT_CONTEXT~ ~w~to ~y~Open ~b~Car ~g~Shop", 1,true,true);  //Here you put the text you want between " "
             secTimeCounter = 10; //Here, we activate closing time counter (Here it's in sec, so 10 sec, if user re-press it restart time counter to 10sec, if you don't want, add Natives:1th example security)
        };
        #endregion
        #region Sec Time Counter  
        if (timeReference <= Game.GameTime)    //With this simple if & its last line, everything in will occur each sec or 1000ms
        {
            if (secTimeCounter > 0) { secTimeCounter--; }; //Each 1000ms, 1 sec pass & so decrease
            if (secTimeCounter = 0) 
            { 
                secTimeCounter--; 
                GTA.UI.Screen.ShowHelpText("~b~Press ~INPUT_CONTEXT~ ~w~to ~y~Open ~b~Car ~g~Shop", 1,true,false);  //Same text, false instead of true
            timeReference=Game.GameTime+1000 //With this simple line, each seconds or 1000ms, we add 1sec before next occurence
            }; //AS always, dont miss the ";" 
        }; //If an error show or if parts of the mods dont load my advice is to check each "if" from top to end !
        #endregion
    }
    #endregion
}
```
With this exemple it will **stop displaying after 10sec** 
If you did **any other way** To end **call the function again with false instead of true for the last agruments !**
***
# **Harder way, In a learning & understanding way** *(or any other goal)* =
**More Time & code needed for the exact same result**, So it's **useful only** for **helping working with native**, as well as **using method/function**, well **Explaining & Understanding all of this**, may help people to understand **how SHVDN is made & works,** *(And maybe contributing to improve/update or doing it their own).* & **Understanding HOW Natives Works** *(Which could be game Changer)*

I recommend creating a **Method in the class ModName : Script**
Depending of **how you wants to show the Help** we will have **different possibility** = *(From easiest to hardest)*

***
## **1st :** Show Help **ONE/EACH tick**
*(Need to call on each display tick so !)* 
[Arguments = Loop: 0 |Shape: 1 to 50]
### **Essential scripts** with no exemples or context :
```cs
FloatingHelpText("~b~Press ~INPUT_CONTEXT~ ~w~to ~y~Open ~b~Car ~g~Shop");//Here you put the text you want between " "
```
### **Exemple Context :** In cover, Health refill, with cost and display ! 
Display an help with a **cost relative** to player health when **Player is low life**, & in **cover since at least 5sec** , 
Then , if player **press the key & have the money**, then **it take money & refill health**
First, we start creating our **method/function** !
```cs
public class ModName : Script
{
    public ModName()
    {
    void FloatingHelpText(string text)
        {
            Function.Call(Hash.BEGIN_TEXT_COMMAND_DISPLAY_HELP, "STRING"); //"STRING" Isn't important put what you wants !
            Function.Call(Hash.ADD_TEXT_COMPONENT_SUBSTRING_PLAYER_NAME, text);
            Function.Call(Hash.END_TEXT_COMMAND_DISPLAY_HELP, 0, 0, 1, 10); //Here the first agruments is always 0/  Second arguments is Loop: 0 or 1/ Third is Beep, always 1 (AFAIK)/ Fourth & last is Scale(aka duration): -1 to 50
        }
    }
}
```
  Now we have our method, lets **call it in our scripts, at EACH tick !** *(Could be **used everywhere**)*
We will start **converting tick/ms in Sec**/1000tick/1000ms,
We will need to **count each second spend in cover,** 
This counter will **restart if player leaves cover,**
& when counter **reach 5** we will **display !**
**NB:** If you use **SHVDN2** stop & use 3, no it's a joke even if 3 is better, just use **UI.Notify** instead of **Notification.Show**
```cs
public class ModName : Script
{
    #region Initilization
    int timeReference = Game.GameTime+1000; //Initialization of time references, used to count in sec
    int coverTimeCounter = 0; //Time spend in cover in sec
    int cost = 0;   //Used to calculate cost of health refill
    bool isReady = false; //Used to know if it's ok to refill player health when key pressed
    #endregion
    public ModName()
    { /*...Your Method/Function...*/ }
    #region OnTick
    void onTick(object sender, EventArgs e)          //You need to know one Tick +- = one ms
    {
        //...Your Method/Function...
        #region Sec Time Counter  
        if (timeReference <= Game.GameTime)    //With this simple if & its last line, everything in will occur each sec or 1000ms
        {
            if (Game.Player.Character.IsInCover == true) { coverTimeCounter++; } //When player is in cover, each sec it add +1, no ";" here because of next else
            else { coverTimeCounter=0; isReady = false; }; //Else restart timer !
            if (coverTimeCounter >= 5 && Game.Player.Character.Health <= 150f) //Check the time in cover and the health
            { 
                cost = (300-Game.Player.Character.Health)*5; //Calculate Health refill Cost
                FloatingHelpText("Press ~INPUT_CONTEXT~ to refill your health for "+cost+"~g~$");  //display help with cost !
                isReady = true;    //Allow refill
            }        //Never any ";" before else
            else { isReady = false; }; //Reset, AS always, dont miss the ";" 
        };
        #endregion
        #region Get User Input
        if (Game.IsControlJustPressed(GTA.Control.Context) && isReady == true) 
        { 
            if (Game.Player.Character.Money >= cost) 
           { 
                Game.Player.Character.Money -= cost;  //Here y -= x is like y = y-x
                Game.Player.Character.Health = (cost/5)+Game.Player.Character.Health;  //Tricky calcul to get health value user paid for !
                Notification.Show("Thanks for your purchase, Your now full Health !");  //Display, Above map (not help)
                isReady = false; //Reset 
            }
            else { Notification.Show("You need more money ! It cost = " + cost + " $"); }; //Above map notif' if it not possible
            timeReference = Game.GameTime+1000 //With this simple line, each seconds or 1000ms, we add 1sec before next occurence
            }; //If an error show or if parts of the mods dont load my advice is to check each "if" from top to end !
        #endregion
    }; //each if need his ";" or "else" each need ";" or another "else" !
    #endregion
}
```
With this exemple it will **stop displaying** when **player** will **move from the Vector3 location**
If you did any other way **To end** obviously **stop calling the function** ;) *(Here when if(World.GetDistance...) increase it just automatically stop calling !)*
***
## **2nd :** Show Help **until its turned off by Same** line 
*(Is turned OFF is the game/scripts reload)* 
[Arguments = Loop: 0 |Shape: -1]
### **Essential scripts** with no exemples or context :
```cs
Function/Method: 
void FloatingHelpText(string text)
        {
            Function.Call(Hash.BEGIN_TEXT_COMMAND_DISPLAY_HELP, "STRING"); //"STRING" Isn't important put what you wants !
            Function.Call(Hash.ADD_TEXT_COMPONENT_SUBSTRING_PLAYER_NAME, text);
            Function.Call(Hash.END_TEXT_COMMAND_DISPLAY_HELP, 0, 0, 1, -1);  //Here the first arguments is always 0/ Second arguments is Loop: 0 or 1/ Third is Beep, always 1 (AFAIK)/ Fourth & last is Scale(aka duration): -1 to 50
        } 
Display/Call:
FloatingHelpText("~b~Press ~INPUT_CONTEXT~ ~w~to ~y~Open ~b~Car ~g~Shop");  //Here you put the text you want between " "
```
### **Exemple Context :** Simple random Dice Game, with Smart display !
Next to the Casino diamond, Pos = x:924 y:47 z:81
First **let's build 2 Function/Method**, a HelpText & a Randomizer
```cs
public class ModName : Script
{
    public ModName()
    {
    void FloatingHelpText(string text)  //HelpText function/method
        {
            Function.Call(Hash.BEGIN_TEXT_COMMAND_DISPLAY_HELP, "STRING"); //"STRING" Isn't important put what you wants !
            Function.Call(Hash.ADD_TEXT_COMPONENT_SUBSTRING_PLAYER_NAME, text);
            Function.Call(Hash.END_TEXT_COMMAND_DISPLAY_HELP, 0, 0, 1, -1); //Here the first agruments is always 0/ Second arguments is Loop: 0 or 1/ Third is Beep, always 1 (AFAIK)/ Fourth & last is Scale(aka duration): -1 to 50
        } 
    void randomizer(int low,int high,out int var) { Random rnd = new Random(); var = rnd.Next(low, high); } //Randomizer function/method using Random().Next()
    }
}
```
Now we have our method, lets **call it in our scripts,** *(Could be **used everywhere**)* 
```cs
public class ModName : Script
{
    #region Initialization
    Vector3 diceGamePosition = new Vector3(924f,47f,81f)
    int timeReference = Game.GameTime+1000; //Initialization of time references, used to count in sec
    bool isNear = false;     //Used to know if player is near
    bool isOpen = false;    //used to know if Help is actually  displayed
    bool gameLaunched = false;  //used to know when the dice game is launched or not
    bool resultDone = true;      //used to know when the dice game result is here or not
    int gameCounter = -1;        //used to count time before result
    int result = -1;          //used to know which result the dice gived us
    #endregion
    public ModName()
    { 
        /*...Your Method/Function...*/ 
        #region Blip Generation
        Blip diceGame = World.CreateBlip(diceGamePosition); //Create blip
        BlipCrate.Sprite = BlipSprite.Casino;   //Set image = icon =sprite
        BlipCrate.Color = BlipColor.GolfPlayer2; //set Colors
        BlipCrate.Name = "Dice Game";        //Set Name
        BlipCrate.IsShortRange = true;       
        #endregion
    }
    #region OnTick
    void onTick(object sender, EventArgs e)          //You need to know one Tick +- = one ms
    {
        //...Your Method/Function...
        #region Control or Input
        if (Game.IsControlJustPressed(GTA.Control.Context) && isNear == true)   //Here we get user input only if player is near dice game !
        {
            if (Game.Player.Character.Money>=25) //Check if player had enought money !
            {
                Game.Player.Character.Money-=25; //take money
                FloatingHelpText("~b~Press ~INPUT_CONTEXT~ ~w~to ~y~start ~b~Dice ~g~Game ~w~! Cost is 25 $"); //Stop Help display
                Notification.Show("Thanks for your purchase, the result will take 3sec"); //Display Thanks message
                gameLaunched = true; //Used to start counter ! Logics usage
            }
            else { Notification.Show("You need more money, at least 25$ !"); }; //else display fails message
        }; 
        #endregion
        #region Result 
        if(resultDone == false && Result > 0) //Check if result is needed
       {
           switch (result) //Here the most complicated part, For each result, this switch will go to associated case: 
           {
               case 1: Game.Player.Character.Money+=100; Notification.Show("~p~Amazing ! You wins the Jackpot ! + 100$ ! 4 Free game more !"); FloatingHelpText("~b~Press ~INPUT_CONTEXT~ ~w~to ~y~start ~b~Dice ~g~Game ~w~! Cost is 25 $"); result = -1;  return;
               case 2: Game.Player.Character.Money+=25; Notification.Show("~g~Nice ! You wins 25$ ! A Free game !"); resultDone = true; FloatingHelpText("~b~Press ~INPUT_CONTEXT~ ~w~to ~y~start ~b~Dice ~g~Game ~w~! Cost is 25 $"); result = -1;  return;
               case 3: Notification.Show("~r~You didn't win anything ! Try again !"); resultDone = true; result = -1; FloatingHelpText("~b~Press ~INPUT_CONTEXT~ ~w~to ~y~start ~b~Dice ~g~Game ~w~! Cost is 25 $"); return;
               case 4: Notification.Show("~r~You didn't win anything ! Try again !"); resultDone = true; result = -1;  FloatingHelpText("~b~Press ~INPUT_CONTEXT~ ~w~to ~y~start ~b~Dice ~g~Game ~w~! Cost is 25 $"); return;
               case 5: Notification.Show("~r~You didn't win anything ! Try again !"); resultDone = true; result = -1;  FloatingHelpText("~b~Press ~INPUT_CONTEXT~ ~w~to ~y~start ~b~Dice ~g~Game ~w~! Cost is 25 $"); return;
               case 6: Notification.Show("~r~You didn't win anything ! Try again !"); resultDone = true; result = -1;  FloatingHelpText("~b~Press ~INPUT_CONTEXT~ ~w~to ~y~start ~b~Dice ~g~Game ~w~! Cost is 25 $"); return;
           }   //return is needed at end of each case to get out of switch !
       }; 
/* Each switch case do : - Give money when win - Display result message - Re-initialize result to -1 - Re-initialize  resultDone to true - Re-Display Help Notif' "Press ... to ..." */
        #endregion
        #region Sec Time Counter  
        if (timeReference <= Game.GameTime)    //With this simple if & its last line, everything in will occur each sec or 1000ms
        {
            #region Get Distance
            if (World.GetDistance(Game.Player.Character.Position, diceGamePosition) < 5f) { isNear = true; } //Here we change a bool depending on player proximity, It allows us to use our isNear instead of SHVDN World.GetDistance(Game.Player.Character.Position, diceGamePosition) < 5f
            else { isNear = false; }; //Then Make sure to have Dis-activator after, like this line
            #endregion
            #region Display & Clear Display
            if (isNear == true && isOpen == false && resultDone = true && gameLaunched = false) 
            { FloatingHelpText("~b~Press ~INPUT_CONTEXT~ ~w~to ~y~start ~b~Dice ~g~Game ~w~! Cost is 25 $"); isOpen = true;}; //When player is Near & Help is NOT open & Not waiting for game result or game starting !
            if (isNear == false && isOpen == true && resultDone = true && gameLaunched = false) 
            { ​FloatingHelpText("~b~Press ~INPUT_CONTEXT~ ~w~to ~y~start ~b~Dice ~g~Game ~w~! Cost is 25 $"); isOpen = false; };  //When player is NOT Near & Help is open & Not waiting for game result or game starting !
            #endregion
            #region Dice Game
            if (gameLaunched == true)  //If the game is launched, start the 3sec counter !
            { 
                if (gameCounter > 0) {gameCounter--; }; //Main Counter
                if (gameCounter == -1) { gameCounter = 3; }; //Start the Counter
                if (gameCounter == 0) {gameCounter--; randomizer(0,7,out result); gameLaunched = false; resultDone = false; };
             }; //End the Counter
            #endregion
            timeReference=Game.GameTime+1000 //With this simple line, each seconds or 1000ms, we add 1sec before next occurence
            }; //AS always, dont miss the ";" 
        }; //If an error show or if parts of the mods dont load my advice is to check each "if" from top to end !
        #endregion
    }
    #endregion
}
```
**To clear the Help User** just **press the key** again !
***
## **3rd & harder :** Show Help **until it's turned off** by different line
*(Keep open even if the game/scripts reload)* 
[Arguments = Loop: 1 |Shape: 1 to 50]
### **Essential scripts** with no exemples or context :
```cs
Method/Function:
void FloatingHelpText(int loop, string text)
        {
            Function.Call(Hash.BEGIN_TEXT_COMMAND_DISPLAY_HELP, "STRING"); //"STRING" Isn't important put what you wants !
            Function.Call(Hash.ADD_TEXT_COMPONENT_SUBSTRING_PLAYER_NAME, text);
            Function.Call(Hash.END_TEXT_COMMAND_DISPLAY_HELP, 0, loop, 1, 10); //Here the first arguments is always 0/ Second arguments is Loop: 0 or 1/ Third is Beep, always 1 (AFAIK)/ Fourth & last is Scale(aka duration): -1 to 50
       }
Start:
FloatingHelpText(1 , "~b~Press ~INPUT_CONTEXT~ ~w~to ~y~Open ~b~Car ~g~Shop"); //Here you put the text you want between " "
End:
FloatingHelpText(0 , "~b~Press ~INPUT_CONTEXT~ ~w~to ~y~Open ~b~Car ~g~Shop"); //Same text, 0 instead of 1
```
### **Exemple Context :** Press F Joke, When player reach 90km/h = 25 M/s
First **let's build a Function/Method**
This one is a **bit different**, it had **2 arguments instead of 1**, It **allow** us to **change the "loop" value** !
```cs
public class ModName : Script
{
    public ModName()
    {
    void FloatingHelpText(int loop, string text)
        {
            Function.Call(Hash.BEGIN_TEXT_COMMAND_DISPLAY_HELP, "STRING");
            Function.Call(Hash.ADD_TEXT_COMPONENT_SUBSTRING_PLAYER_NAME, text);
            Function.Call(Hash.END_TEXT_COMMAND_DISPLAY_HELP, 0, loop, 1, 10); //Here the first agruments is always 0 / Second arguments is Loop: 0 or 1/ Third is Beep, always 1 (AFAIK) / Fourth & last is Scale(aka duration): -1 to 50
        }
    }
}
```
  Now we have our method, lets **call it in our scripts,**
```cs
public class ModName : Script
{
    #region Initilization
    int timeReference = Game.GameTime + 1000;  //Initialization of time references, used to count in sec
    bool isHelpActivated = false; //Boolean to check if the help is on or not
    #endregion
    public ModName()
    { /*...Your Method/Function...*/  }
    #region OnTick
    void onTick(object sender, EventArgs e)          //You need to know one Tick +- = one ms
    {
        //...Your Method/Function...
        #region Sec Time Counter  
        if (timeReference <= Game.GameTime)    //With this simple if & its last line, everything in will occur each sec or 1000ms
        {
            if (Game.Player.Character.Speed >= 25f) 
            { FloatingHelpText(1,"~b~Press ~INPUT_VEH_EXIT~ ~w~to ~y~have ~b~LOTS ~w~of ~g~FUN !"); isHelpActivated = true ;} //no ";" after this if because of next else, When player reach 25m/s = 90km/h it display the text/joke
            else 
            { 
                if (isHelpActivated == true) //Check if help is actually displayed, avoid closing already closed display
                { 
                      FloatingHelpText(0,"~b~Press ~INPUT_VEH_EXIT~ ~w~to ~y~have ~b~LOTS ~w~of ~g~FUN !");
                      isHelpActivated = false; 
                }; 
            }; //If not, stop the display
            timeReference = Game.GameTime+1000 //With this simple line, each seconds or 1000ms, we add 1sec before next occurence
            }; //AS always, dont miss the ";" 
        }; //If an error show or if parts of the mods dont load my advice is to check each "if" from top to end !
        #endregion
    }
    #endregion
}
```
With this exemple it will **stop displaying if speed <25m/s** or <90km/h
If you did **any other way** To end **call the function again with 0 instead of 1 !**
***
## Conclusion & End
Then **it should work** ! If not **fell free to ask** ! 
If anyone **need help** it will be a **pleasure** for me,
I'm not a robot, due to the size of this (those?) tutorial, Mistake are possible !
Any constructive advice or unseen miss report will be appreciated
Also if anyone have any suggestion/modifications to make the code better I'm open minded ;)
**I really hope it will help someone**, has it took me several day to fully understand and find how to :P
See you & have fun !