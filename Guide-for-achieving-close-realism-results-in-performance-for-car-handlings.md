**Introduction**:

**Huge thanks to ikt(https://forums.gta5-mods.com/user/ikt) for his corrections and scripts.**
**Do look at the comments for added inputs and corrections, although I try to include their additions to this main post as quickly as I can.**

Hi, I am a huge car enthusiast and an amateur Miata racing driver and I quench my thirst for experiencing high-end performance cars through video games. I cannot run modern racing sims so I make do with tweaking GTA 5 handling attributes to bring the car as close to realism as possible. 



After spending nearly a month on several Porsche and Ferrari mods, I feel like I've had enough experience to guide my fellow petrolheads to gain the ability to edit handling files to a fine level of detail.



"When there's dozens of handling editing guides out there, who am I to make one?", you may ask. 



Ans- I myself referred to those guides in the beginning, however, by the time I was through with my weeks long testing, I felt those guides were incomplete, so here's my 2 cents; an attempt to fill their gaps, if you like.



**What you'll need:**



In game handling editor(https://www.gta5-mods.com/tools/real-time-handling-editor) to make life easy. 

G-force meter(https://www.gta5-mods.com/scripts/g-force-meter) to test response and grip.

Speedometer(https://www.gta5-mods.com/scripts/speedometer-improvedalexbladeversion) for obvious reasons.

Stopwatch(https://www.gta5-mods.com/scripts/stopwatch-for-testing-cars) to test overall acceleration and quarter-mile timing.

Enhanced Native Trainer(https://www.gta5-mods.com/scripts/enhanced-native-trainer-zemanez-and-others) for misc stuff and **for its odometer**, a feature we'll need (Enable it in Vehicles->Show Current Mileage). It is great for **measuring distances in game**.

Custom Gear Ratios(https://www.gta5-mods.com/scripts/custom-gear-ratios) Look up your car's real life gear ratios online and the final drive gear ratio and note them down. You'll need them to simulate spot on acceleration and top speed like the real life car.

Optional:

Nurburgring Nordschliefe(https://www.gta5-mods.com/maps/nurburgring-nordschleife-circuit-hq) and Nordschliefe MiniMap(https://www.gta5-mods.com/scripts/vans123-s-nurburgring-nordschleife-minimap): highly recommended, the main straight is excellent for testing the acceleration and quarter mile times of the car. The overall track is great to test out final results and enjoy the fruits of your labor. (Which WILL be quite laborious, believe you me.)

Manual Transmission(https://www.gta5-mods.com/scripts/manual-transmission-ikt) if like a true car guy you want to test each gear to a fine detail.

VStancer(https://www.gta5-mods.com/scripts/vstancer): to easily stance the ride height and wheel characteristics. 



Huge thanks to the creators of each of these mods/scripts. Couldn't have done it without you :)



**Getting Started**:



Before we proceed onto editing the handling itself, it's best to get acquainted with the tools we'll be using to go about our business.



1. The G-force meter(https://www.gta5-mods.com/scripts/g-force-meter) comes in the center of the screen as standard. Move it to any corner of the screen you like by referring to the mod's guide.



2. The Speedometer(https://www.gta5-mods.com/scripts/speedometer-improvedalexbladeversion) is a fantastic mod that auto selects the best gauge depending on the car you're driving. 



3. The Stopwatch(https://www.gta5-mods.com/scripts/stopwatch-for-testing-cars) is a **critical** tool that helps in many major ways: 



   a. It can measure your 0-100 kph or 0-60 mph as well as your 100-200 kph. It resets a timer that starts exactly when you hit the throttle. 



   b. Every time you stop and restart the timer, your get teleported to the starting location, which is great as you'll need to do full bore starts dozens of times.

   

   **c. (Important)** It comes with a "Map" menu of which you can edit the config file outside the game. In which you can specify your own starting and ending locations of your test track. Use the ENT(https://www.gta5-mods.com/scripts/enhanced-native-trainer-zemanez-and-others)'s "Show coordinates" feature to obtain the coordinates as well as heading at any place in the game. Now record the coordinates on the Nurburgring(https://www.gta5-mods.com/maps/nurburgring-nordschleife-circuit-hq) where you want the start and end points to be. You can also use the **odometer** to measure out a 1/4 or 1/2 mile on the straight to set your starting and end points said distance apart. This is a great way to preset this car testing tool. You can do dozens of well timed Launches within minutes this way.



4. The in game handling editor(https://www.gta5-mods.com/tools/real-time-handling-editor) is absolutely necessary unless you want to pull your hair out trying to edit the handling by restarting the game every time you change a little value. A little tip: Assign a key to this mod in its config file, as typing 'rthe' in the console every time can get quite tedious. When you create a handling file using this mod, you need to close and reopen the script menu to load the saved file in your load menu or it won't appear. Also don't forget to keep saving your edits in new files periodically, as you can lose your progress easily plus if you make a mistake during editing it's easy to go back to the last stable edit instead of fussing over where you made a mistake. Always respawn and test your car after each small edit or you'll screw up quite easily.



5. The VStancer(https://www.gta5-mods.com/scripts/vstancer) is best to stance your car and to perfectly tune wheel characteristics and suspension height, but **only use it once you are done editing your handling!!** As it can screw with the handling editing process. Once you are satisfied with the final handling file you created, copy that handling into the car's .rpf. The in game handling editor doesn't do that for you, you need to replace the handling.meta file manually at the end yourself.



**The Guide:**



I myself began making edits after reading this excellent guide by Eddlm(https://forums.gta5-mods.com/topic/24280/understanding-and-editing-gtav-s-handling/2), so you can give it a quick read if you like but I do cover everything in good detail. So you can skip it without any problem at all. Also, I went on to find that this guide does not talk about quite a few very critical handling values which I shall.



  **The constraint:**



It is quite possible to obtain a **very** realistic handling in GTA V, although I have to say that the way you'd think a car works in real life, is quite far from how the handling.meta files are built and used. For e.g. there is no equivalence of real life car kerb weight and horsepower in GTA V. The Car's **fMass value** has no bearing on its handling and there is no way to build an equation between the **fInitialDriveForce value** and say the horsepower and torque figures of a real car. You can't translate 500 or 600 hp into a **fInitialDriveForce** value using some formula, if you know what I mean. It all has to be done through **trial and error** to ***simulate*** said amount of horsepower. Similarly the drag coefficients of cars in real life translate poorly into the **fInitialDragCoeff value**. Again, **trial and error is the name of the game**.


**THAT SAID, LET'S START:**

I shall use the example of a 991 GT2 RS by AreanLee(https://www.gta5-mods.com/vehicles/porsche-911-991-gt-2-rs-weissach-edition-2018-hq-interior-hq-exterior-hq-light-replace-add-on) that I tuned to near perfect realism, if I may say so myself. 


First things first, abbreviations: 


**"Car's real life"/"Real Life Car" : CRL**

**"991 GT2 RS's real life value ": RV**

**"The value I put in": MV**

Steps:

Fire up the RTHE(https://www.gta5-mods.com/tools/real-time-handling-editor), go to "Edit Current Handling" and don't forget to save each time you edit. Select Respawn Vehicle to apply any changes made to car.

Before you start modifying stuff, think about what you want your final car to look like, whether you'll be using fat race slicks ([like this le mans wheel](https://www.gta5-mods.com/vehicles/lemans-wheel-add-on)) or low profile street tyres. As we'll be taking these things into account when tuning to ensure the aesthetics match the functionality. If you'll be lowering your car, make sure to keep in mind that you'll want to add a bit more downforce than suggested here.

If you are using a slick with a large sidewall on a performance/racecar, enable the **HF_TYRES_CAN_CLIP** flag under **strHandlingFlags** as you'll be tuning *with* this flag enabled first. If you enable it after you tune, it might screw up your entire work. Otherwise, if you're using low profile tyres, leave it disabled.

Think about whether you want engine braking, if not enable **HF_FREEWHEEL_NO_GAS** under **strHandlingFlags** now as we'll be tuning our brakes with this pre-enabled or pre-disabled. If you change it after, it may or may not have an effect on the overall braking.


**Chassis**





* **fMass value:** Completely inconsequential to the way the car will handle unless during a collision with an object, during which the game uses this value to simulate Newton's 2nd and 3rd law. Otherwise, absolutely useless. 



   Set it to your CRL kerb weight to simulate realistic recoil when colliding with a dump truck for example.

        RV: 1243 kg
        MV: 1243.00


* **vecCentreOfMassOffset:** Using RTHE(https://www.gta5-mods.com/tools/real-time-handling-editor), you can visually see where the center of mass of the car the game computes to be. (Make sure the instance of your spawned car is the only one so you don't have to restart the game to apply the changes made to **vecCentreOfMassOffset** value). Otherwise, if you spawn multiple cars, you need this tool(https://www.gta5-mods.com/tools/com-tools) by Eddlm.


* 1. Using the **Y value**, bring it forward to right on top of the front axle. Note the value. Now take it all the way back to the rear axle, note the value again. Calculate the **gap** between two values. Now find your CRL weight distribution, if its 50-50, set value to the middle of the gap. If it's 60% front and 40% rear, set the value 0.4xgap away from the front. If it's 65-35, set it .35xgap away from front. You get the gist. Basic Math. 



                RV: 61% rear 39% front. Hence .39xgap away from the rear axle value.
                MV:  -0.36



* 2.  **X value**: Visually set it to right smack dab middle of your car's model to simulate perfect 50-50 weight distribution between the tire track, as most cars have it like that.



                RV: 50-50
                MV: 0.00





* 3.  **Z value:** Hard to say where this should be, as manufacturers generally do not release where exactly the centre of mass lies vertically, although they do try to get it as down low as possible, especially on performance cars. You can visually estimate where it should be on your car, imagining how high or low the engine is in the CRL, how big it is, how heavy the transmission is and how high/low  it is placed, whether or not your CRL has a carbon fiber hood or roof etc etc.



                RV: ??
                MV: 0.09 (Quite low as Porsches have low lying Flat 6's and low lying PDK + Carbon roofs and hoods)





* **vecInertiaMultiplier:** This is the Sweet and Sour MOMENT OF INERTIA. For laymen, how much *away* the actual mass of the car lies from the 3 axes of rotation intersecting at the Center of Mass we just set. These determine how easy or hard it will be for your car to resist angular accelerations, aka changes in roll (X), pitch (Y) and yaw (Z). The further away the mass lies from an axis, the harder it is to turn about that axis, and the higher its value is.



   As with most values, I could not find a correlation between values to put in and real life Moments of Inertia in Cars. Although fair to say, nobody actually knows these values for CRLs either. 



   But think of it this way: Looking at the front of the car, the mass *looks* to be closer in to the roll axis than the yaw axis looking from the top. Therefore, Roll should be less than Yaw. Although, it is fair to say CRL have Roll < Pitch too but if you try to make it so in GTA V, the handling gets Wonky. So keep it like this **Pitch < Roll < Yaw**. The gap between pitch and roll should be less than that between roll and yaw to simulate at least an ounce of realism.



           RV: ??
           MV: pitch x="1.070000" roll y="1.125000" yaw z="1.200000"
 


**Body:**



* **fInitialDragCoeff:** The car's drag coefficient. Translates poorly to CRL drag. Weaker than CRL drag at low speeds and stronger than CRL drag at high speeds, regardless of the value set. However, there is **a way** to get it right, *sort of*.



However, to tell you what it is, I have to digress from the **Body** section for a while, as it is closely linked to the **Engine** section.



"**Body *and*  Engine**" Section:



There are 5 values that determine A to Z about a cars acceleration and top speed.



These 5 values are 



* **fInitialDragCoeff**   

* **fInitialDriveForce**

* **fInitialDriveMaxFlatVel**



* **fDriveInertia**

* **fEngineResistance**



The first 3 are the most important and their operation is very complicatedly intertwined with each other. So let's cover the last 2 first.



* **fDriveInertia:** ~~How much inertia your car shows against acceleration and braking, since fMass is pointless, this can be used to simulate a 'heavy' body. You can edit this if you like, but it's best to leave it at 1.00, as we can simulate realistic acceleration and braking using other values.~~ 

  **ikt's correction**
"To my knowledge, just how fast the engine can rev freely. Doesn't have much of an impact, aside from simulating a fast-revving or slow-revving engine (e.g. big engine with lots of internal mass)"

  To tune **fDriveInertia** , watch a video of your CRL being revved in neutral and then edit this value depending on how fast or slow you want the engine to rev while stationary. Unless you deviate too far away from a value of 1.00 (don't get close to 0.00, especially) you don't need to worry about it affecting your acceleration, as we'll tune that with other values. You can safely approach ~2.5 if you want to replicate a really fast revving small stroke Naturally Aspirated Engine.


          MV: 1.80



* **fEngineResistance:** Imagine this as a massive brake continuously applied on the engine. Makes sense? No? Exactly. Leave it at 0.00.

      MV: 0.00

"**The Speed Procedure:**"

**Before you carry on with this**,  Now is a good time to dial in your gear ratios and top speed using **ikt**'s CGR script(https://www.gta5-mods.com/scripts/custom-gear-ratios). **DO IT NOW.**


**fInitialDragCoeff**   **fInitialDriveForce** and **fInitialDriveMaxFlatVel** each must be tweaked keeping the other 2 in mind.

**fInitialDriveMaxFlatVel** becomes of no consequence if you have setup your gearing using CGR(The method I recommend). You will have to set your CGR to autoload set gearing each time. Skip the following bullet point if you have done it. Else do it this way:

* **fInitialDriveMaxFlatVel:** Set this first. This sets the max possible speed your car can achieve assuming 0 drag and a runway as long as it needs. Imagine this as a purely mechanical limit, that is, the theoretical max speed of your CRL, purely a function of the max engine RPM, Top gear ratio, the Final drive gear ratio and wheel diameter. Many online tools are available to calculate this. Changing your wheel diameter in game however, does not affect this. Your car will still chase after the top speed you specify here. Use an online tool like [this one](https://spicerparts.com/calculators/transmission-ratio-rpm-calculator) to get your top speed.

   **Using CGR to set your top speed makes this value irrelevant.**

           RV: 7200 Max engine RPM, 7th gear ratio 0.67:1, Final drive gear ratio 3.96:1 
           and wheel size 325/30 - ZR21. 
           
           Giving me a theoretical top speed of 231.8 Miles per hour for the 
           CRL 991 GT2 RS.
           So the value you need to put in here is given by
           
           fInitialDriveMaxFlatVel = (0.9 * 231.8(Top speed in km/h)) / 1.2
                                   = 173.85
           MV: 173.85



* **fInitialDriveForce:** With the **fInitialDragCoeff** set to 0.00, slowly increase this value and do repeated launches using the Stopwatch(https://www.gta5-mods.com/scripts/stopwatch-for-testing-cars) mod. Measure your 0-100 kph times as it is at low speeds where drag has little effect IRL. Keep increasing this value until your 0-100 kph times are *juuuuust* a little faster than the CRL.



          MV: 1.00 (to obtain 0-100 kph of ~2.775 seconds with 0 drag, i.e. just a little faster than RV time of 
          2.8 seconds)



* **fInitialDragCoeff:** Once you're satisfied with your  **fInitialDriveForce** value, start increasing this value. Keep increasing it until your 0-100, 100-200 as well as 0-300 times and the real top speed also get back up to realistic times. Once you're through with this, voila! You have achieved ~98% realistic acceleration and top speed.



          MV: 2.35 (to finally get 0-100 of 2.845 seconds, 0-200 of 8.354s and 0-300 of 22.500 seconds). 

Which is quite close to the real times of a GT2 RS - [2.8s, 8.3s and 23s](https://accelerationtimes.com/models/porsche-911-gt2-rs-991) respectively.



Bear in mind though that it is impossibly hard to simultaneously get each of these times absolutely right to the dot. Either your 0-100s start getting too fast or your 100-200 get too slow. Now maybe because the fact that GTA V doesn't use actual kerb weight and BHP physics makes this impossible, or maybe editing <*insert unknown parameter here*> can actually sort  this out, but the sheer number variables to be adjusted simultaneously gets too damn high at this point. You'll start clawing your eyes out from the frustration. So I advise against doing that. Just accept close enough times and move on. 



Getting back to the **Body** section.



* **fDownforceModifier:** I was unable to correspond this value with the actual downforce of a real GT2 RS in kg-force units. However, it is possible to get somewhat of an idea about what to put here. Watching an actual GT2 RS lap nurburgring, you can tell where the car almost gets off the ground and at what speed, especially at that little jump near Flugplatz. So by going that speed on that jump you can change the downforce until you are able to simulate similar "lifts" - or lack thereof.



           MV: 1.75



**Suspension**



* **fCamberStiffnesss:** Leave it at 0.00. It is said this value has no effect at -1.0 or 1.0 but I couldn't help but feel unwanted "wonkyness" that I didn't at 0.00. If you manage to understand how this works, by all means, go ahead and edit it. Hit me up and let me know as well.



* **fSuspensionForce:** Literally what it says. How much force is in your suspension. High value is stiff springs, low value is soft springs. Race cars should be 3.00 or more. But the difference isn't really noticeable once it's above ~2.5, i.e., 3.5 and 10.0 feel the same.


 
           MV: 3.30



* **fSuspensionComp/ReboundDamp:** In the real world, dampers accomplish 3 things. Preventing the suspension from bottoming out on either ends. Remove unnecessary vertical oscillations, and dampen weight shifting of the car to increase stability. Compression damping is important for the suspension not bottoming out on a bump and rocking the car suddenly, while rebound damping ensures the light unsprung mass doesn't hit the road too hard and destabilize the car on the return. You need more rebound damping than compression damping, as the heavy sprung weight counteracts the spring during compression, but the lightweight unsprung mass can be shot downwards by the spring without strong rebound damping. Flipped around for race cars as they sacrifice comfort for maintaining contact with the road at all times. Why did I tell you all this? I don't know. 



           MV: 1.80 Compression and 1.35 Rebound



* **fSuspensionBiasFront:** This value makes no sense in the real world. It is a cheat value that balances your suspension for you so you don't have to. Gives suspension "strength" to front or real axle depending on the bias value. Quite simple to tune this really. If you have setup the Y coordinate of **vecCentreOfMassOffset** as shown above, you know the weight distribution of your car. Which is also exactly the strength distribution you'll need, for obvious reasons. 0.0 is all strength to rear and 1.0 is all to front. If you don't do this, your car will appear to slant onto one end or the other.



          RV: 61% rear and 39% front weight distribution.
          MV: 0.39



* **fSuspensionUpper/LowerLimit:** With **fSuspensionForce** set to 0. Visually set the lower limit to whatever you feel should be the lowest limit before the car bottoms out. Restore **fSuspensionForce** to original value. Flip the car onto its roof. Visually set the upper limit to whatever you feel should be the highest limit before the springs bottom out. Passenger, luxury and offroad cars have more suspension travel, race cars have less.



          MV: up 0.08,  low -0.09



* **fSuspensionRaise** | **fToeFront** | **fToeRear** | **fCamberFront** | **fCamberRear** and **fCastor** are best modified visually using VStancer(https://www.gta5-mods.com/scripts/vstancer). In the real world these 6 values would have a mountain of an effect on the overall handling, but in GTA 5 the difference wasn't noticeable for me. Also these values can barely be changed, as the wheels start to look out of place quite easily. Unless of course you're slamming your car. In which case, **WHY**?



**Transmission and Steering**



* **fDriveBiasFront:** 0.00 is RWD and 1.00 is FWD. Anything in between is AWD. If using AWD, change this value depending on your car's weight distribution. If 60% front 40% rear, for example, set to LESS THAN OR EQUAL to 0.60. "Less than" because while accelerating the weight shifts further to the rear than it is when stationary. Therefore best to keep a few notches lower than the actual weight distribution for theoretically maximum traction when accelerating mimicking a computer controlled Launch Control found on modern AWD cars.



          MV: 0.00 (GT2 RS is RWD)



* **nInitialDriveGears:** The value you put in here is also the top gear you'll get, unless you've edited your gearbox tuning(which you probably must have by now), which *adds another* gear. So, if your car has 7 forward drive gears, set this to 6. If your car has 6 forward gears, set to 5. You get the idea. But again, if you still haven't done it, IT'S BEST TUNE YOUR GEARBOX WITH CGR(https://www.gta5-mods.com/scripts/custom-gear-ratios) to completely bypass having to edit this value at all.

  Use Manual Transmission(https://www.gta5-mods.com/scripts/manual-transmission-ikt) to test each gear in detail.
 

         MV: 7 (7 speed PDK transmission)



* **ClutchChangeRateScaleUp/DownShift:** 0.9 over this value is how much time in seconds it takes for your car to up/downshift. 10 means car shifts in 0.09s. 5 means in 0.18s. 0.5 means it takes 1.8 seconds.



          RV: PDK's are nearly instantaneous. I assume 10-20 milliseconds.
          MV: 80 (shifts in 0.9/80 = 11.25 milliseconds)



* **fMaxDriveBiasTransfer:** ikt and most veterans say it has no effect, but I couldn't help but feel something when I changed it idk why. It felt like it made a world of difference on FWD or RWD cars too **(No, it doesn't make FWD/RWD cars become AWD)**. 

   **This value probably doesn't have an effect if the ones more experienced than me say so**, and so if that's the case, setting it to 1.00 isn't gonna matter anyway. So I recommend doing it just to be safe. -1.00 (the default value usually) made my handling suck incredibly more, it felt like.



          MV: 1.00



* **fSteeringLock:** Sets max steering angle. Find your CRL's real life turning circle diameter. Use Odometer to measure out said distance somewhere in game. Place 2 bollards at ends of this distance using ENT(https://www.gta5-mods.com/scripts/enhanced-native-trainer-zemanez-and-others). Tweak this value till you're able to make a U-turn between these bollards.


 
          MV: 35.00



**Tyres**



* **fTractionCurveLateral:** The max angle between your model and the velocity vector of your car assuming slippage before it gets uncorrectable with steering (starts to drift). Race cars have a less forgiving driving dynamic, lower it for them. Rally cars can handle more slippage and still return to stability more easily. Best to just leave at 22.50 if you don't know what you're doing.



         MV: 22.50



* **fLowSpeedTractionLossMult:** Set to 0.0 for realism. More than that for "cool" burnout effect when launching.



         MV: 0.00 duh.



* **fTractionBiasFront:** 0.0 gives all the traction to the rear wheels, 1.0 to the front. Traction is a fancy word for what is basically friction (at least for video game purposes). And friction is a product of 2 things: Normal force and coefficient of friction. Coeff of friction depends on things like tyre compound, width and temperature in real life. This is a static value IRL and should be static in the game as well. While Normal forces depend on nothing but the weight distribution at any moment. And since weight shifts as you drive the car, so this is not a static thing IRL. However GTA V does ask you for a static value for this entire field. I would recommend that you go with whatever your weight distribution is on the CRL + bias it a little rearwards for realism as well as traction while accelerating if your CRL is forward weight  biased. If it is rear biased (like a porsche) then you need not shift it rearwards anymore than the weight distrib itself as it could screw the front end and make braking/turning a nightmare.

         MV: 0.45



* **fTractionLossMult:** Multiplies traction lost on rough surfaces with this value. Racing Slicks and Drag radials have higher value. Treads have lower. Racecars have higher value, offroaders have lower. Never bring it below ~0.50 for the sake of realism, even for dedicated off-roaders.



         MV: 1.80



* **fTractionSpringDeltaMax:** No idea what this does. Leave it at less than 1.00.



         MV: 0.8



* **fTractionCurveMin/Max:** The holy grail. The forbidden fruit. The femme fatale. Increasing this value makes car faster,  grippier and more fun. Decreasing makes it, well, realistic. No road car, not even $400,000 Porsches can pull >1.5 Gs. But all default GTA V cars, even the crappy, 70s sedans are coded to pull Formula 1 level >2.0Gs. Set to the value of your choice. But remember realistic values are painfully difficult to control in this arcade based game. So if you're up for the challenge, by all means GO FOR IT! It is quite a joy in itself to be able to slowly master a fast <1.5 G car in GTA V. Especially if done on the Nurburgring mod!



         RV: Min 1.17 Max 1.46
         MV: Min 1.45 Max 1.46 (if min value is set any lower, acceleration starts to get slower than IRL)



**Brakes**



* **fBrakeBiasFront:** Most cars are forward biased. Racecars are heavily forward brake biased to reduce understeer while braking into a turn. 0.0 gives all brake force to rear wheels, 1.00 all to front.



         MV: 0.85



* **fBrakeForce:** Based on real life brake-bite mechanism. Find your CRL's 100-0 braking distance. Use Odometer to measure out said distance somewhere in game. Place several bollards between this distance using ENT(https://www.gta5-mods.com/scripts/enhanced-native-trainer-zemanez-and-others). Tweak this value till you're able to brake 100-0 kph between these bollards for braking realism.  Too high value will lock wheels unless ABS flag is used. 



         MV: 0..87 (for realistic 27 meter 100-0 kph braking distance of GT2 RS). Use more than 1.00 for easier 
         arcade-y braking. 



* **fHandBrakeForce:** Affects rear wheels only. Brakes rear wheels on passenger cars IRL. Locks up rear wheels on race cars IRL. Anything over 0.65 is enough to lock rear wheels.



         MV: 1.5



   Important: Pay attention to strModelFlags. **AbsStd** simulates arcade-y version of a high performance modern ABS (Easiest Difficulty, perfect static friction, 0 slippage, max G's, stiffer turns). **AbsAltStd** simulates older/GT-Daytona racing style ABS (Medium Difficulty, realistic brake pumping, some slippage, looser turns). "Abs/AbsAltOption" disables ABS unless brake upgrades are equipped (Highest difficulty, kinetic friction, full slippage, pure race car realism). Though you don't have worry about brakes locking without any kind of ABS even at full brake pressure unless you're using a ridiculously high **fBrakeForce** value of ~2.3 or greater.

If **AbsStd** is used, your car is able to utilize all of the braking g's set by **fTractionCurveMax**.  Only your fBrakeForce value needs to be at a certain minimum threshold to take advantage of this. Any more brake force has no effect on actual braking, like a true brake bite system coupled w/ perfect arcade-y ABS.

**Anti Roll Bars**



* **fAntiRollBarBiasFront:** 1.0 Assigns all anti roll bar bias to front axle. 0.0 to rear. Set to 0.5 for equal roll negation.



         MV: 0.50



* **fAntiRollBarForce:** 0.0 = anti roll bars absent. 1.00 = body roll nullified completely. Race cars have higher value.



         MV: 0.95



* **fRollCentreHeightFrontRear:** Roll centers aren't fixed IRL and migrate when the car rolls. These usually should be just below the Roll axis going through the vehicles center of mass. Adjust until the visible roll center lines are just below the car axles. Incorrect values (roll center above the axle) will cause the car to have negative roll defying the laws of physics.

         MV: 0.18 each.

And that should be it. Play around with other handling and model flags. Comment if you learn something new I did not mention. Let me know about any mistakes I might have made.