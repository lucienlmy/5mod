I have been tinkering with this since the GTA V release in April of 2015. For much of my efforts, the struggles I have had, have been a great many. Of recent though, I have finally cracked the mystery of why densities were so easy to increase in the countryside and freeway, but much more difficult to get a handle on in the city. Finally getting what I was after all along, I have decided to share here, with the community, how to go about getting much, much more traffic in your game without your PC chucking itself out the window, LOL...
 
I am aware that on gta5-mods.com there are mods that do this, but I have reviewed and tested them all, and they don't get anywhere close to what I have managed to pull off. I will be demonstrating here, why that is the case, and how to fine-tune everything to get that near picture-perfect feel. Trust me, when you get this in your game, the feeling is absolutely glorious. 
 
We will need to make edits to two files, which are popcycle.dat and gameconfig.xml. Other's who have brought to the mod site their version of increased traffic densities, outright neglected any attention to  several parameters in the gameconfig, which are absolutely necessary to get these inner cities traffic really ramped up. 
 
First up, we must deal with popcycle.dat. Below we have a snippet of an entry for Rockford Hills shopping district. If I were to do the same for the countryside, the traffic would be so over-the-top, it wouldn't even resemble what the countryside would really lool like. So this is how I have it for anything inner-city, except a few exceptions like terminal island and Port of Los Santos which would not be nearly as populated. In the countryside, I have set the quantity of cars to spawn at 50, the freeway I have set to 300. Other rural areas like cult, slab, and sandy shores, prison area to about 30.
 
POP_SCHEDULE:
ROCKFORD_HILLS_SHOPPING
// Weekday
//
//  #Peds  #Scenario #Cars  
     100     20       600   
      50     10       600   
      50     20      600   
      65     25       600   
     100     50       600   
     200     50       600   
     200     50       600   
     200     50       600   
     200     50       600   
     100     50       600   
     100     35       600   
     100     35       600  
 
Keep in mind, that the 600 is not what will actually spawn in game, as we will soon see. Next up we examine the vehicle section of the gameconfig - we will see exactly why the vanilla-state of the game looks so absolutely barren.
 
<VehicleAmbientDensityMultiplier_Base value="156"/>
<VehicleAmbientDensityMultiplier value="200"/> 
 
This group (above) doesn't do what other modders thought in their own traffic density mods. You raise these values to 25k and nothing changes, nothing.
 
<VehicleMemoryMultiplier value="6000"/> - needs to be increased beyond the default, to allocate the necessary quantity of memory to spawn the amount of traffic I want to see in-game. Still not enough yet, as we will continue to see.
 
Below we have what I believe is a safeguard. The base value is what we start with, and the next value is telling the game-engine "give me this, if you can". So we start with 160, and if the vram and CPU is enough to give more, it will do so.So we will get somewhere between 160 - 520  vehicles PER ZONE - not as in on the entire map.
 
<VehicleUpperLimit_Base value="160"/> 
<VehicleUpperLimit value="520"/>
 
So far though, not much has changed because there are other parameters that also must be adjusted to provide enough space for the cars to spawn in, AND we must set the culling to occur AFTER the max creation distance!
 
Neglected by other modders is this section right here - 
 
<VehicleKeyholeShapeInnerThickness_Base value="10"/>
<VehicleKeyholeShapeInnerThickness value="10"/>
<VehicleKeyholeShapeOuterThickness_Base value="130"/>
<VehicleKeyholeShapeOuterThickness value="130"/>
<VehicleKeyholeShapeInnerRadius_Base value="10"/>
<VehicleKeyholeShapeInnerRadius value="10"/>
<VehicleKeyholeShapeOuterRadius_Base value="115"/>
<VehicleKeyholeShapeOuterRadius value="115"/>
<VehicleKeyholeSideWallThickness_Base value="20"/>
<VehicleKeyholeSideWallThickness value="20"/>
 
Most important section of the config, because this will define how much real estate we have to spawn cars from what we can see forward of us, behind us, and to either side of us - this will make more sense when we are within the vicinity of a four-way intersection. Game-engine needs to know how far away from were I am at a moment, how far back from me, am I given space to spawn traffic in ALL four directions? Think of a square or say a rectangle. We alter these values to create a square that you are always in the center of. The bigger the radius of the square we create, the more vehicles will spawn inside of it, as long as we are culling vehicles outside of this square we are creating.
 
InnerThickness_Base value="10" - this is defining how close cars are to spawn when they are beside me. If I am looking forward, there are still areas to spawn traffic to the left and right of me.
 
OuterThickness_Base value="130" - ok, now it needs to know how much real-estate it has behind the nearest spawned vehicle to spawn additional traffic? As you can see, I pulled the inner value in real close, and pushed the outer value out way more so than the default values, to ensure there is plenty of room to spawn the quanity of vehicles I expect to see in-game.
 
InnerRadius_Base value="10"/> -This is all about what is spawning in front of you!  The idea here, is I want to bring in the radius so I create more real-estate for traffic to spawn in. The larger the value the less traffic I will have.
 
OuterRadius_Base value="115"/> - Very tricky to get right. This is for a "second wave" of vehicles spawned beyond our inner radius. Any vehicles within this outer radius that spawn after max creation distance are merely for show as they are the lowest of it's LOD models, and don't even have collisions. They are merely "mirages" that float above the ground, if you get close enough to see them up close. If you did try to get close enough, they will start rapidly de-spawning. Vehicles that spawn in the outer radius within max creation distance "bleed" into the group in the inner radius, but if culling occurs before where they spawn, they will disappear as soon as they spawn.
 
SideWallThickness_Base value="100"/> -  Only yesterday, and by accident, did I discover what this does. You can also see sideways. Yesterday, when I fired up the game, I happened to spawn at a location where I was behind a building, facing towards a freeway across from me which was moving left to right. I noticed that the traffic was disappearing just as it started getting closer to my position. Well, as part of testing days before, I had lowered that value to 20. So I logged off, and pushed that value out to 100. I fired up the game, and now the traffic was driving right past me! So the smaller the value the less real estate there is for traffic to spawn in - increasing the value, increases how much traffic will spawn in a radius that moves from left to right or vice versa when you are facing any situation that involves you looking at traffic that can only move left or right.
 
<VehicleMaxCreationDistance_Base value="400"/>
<VehicleMaxCreationDistance value="400"/> - this tells the game-engine how far out it is allowed to spawn a vehicle. You starting to see just how complex it really is to get traffic densities right in a game like this? If you do not account for what each paramter will do when changing it, it can undo what you are really after. 
 
<VehicleMaxCreationDistanceOffscreen_Base value="100"/> - same thing as above but for what is spawning behind us. R* had it at 50, but it's just too low man! It means I will see very little traffic once I turn in the opposite direction! I could set it higher, but performance will suffer because we are already - at this point - doing WAY more than R* default values!
 
<VehicleCullRange_Base value="621"/>
<VehicleCullRange value="621"/>
<VehicleCullRangeOnScreenScale_Base value="450"/>
<VehicleCullRangeOnScreenScale value="450"/>
<VehicleCullRangeOffScreen_Base value="150"/>
<VehicleCullRangeOffScreen value="150"
 
 
Remember I said we need to set culling after the max creation distance? Looking at these values you can clearly see that is exactly what I have done here. Think about how counter-productive it would be to have vehicles culled before the max creation distance (which R* does with it's default values). It would mean I would not only be killing off vehicles I want to see when I come around a corner that is obstructed by a building, but then also I would be treated to cars now spawning right before my eyes!
 
 
<DensityBasedRemovalRateScale_Base value="72"/>
<DensityBasedRemovalRateScale value="72"/>
<DensityBasedRemovalTargetHeadroom_Base value="20"/>
<DensityBasedRemovalTargetHeadroom value="20"/>
 
Values above is responsible for how quickly to despawn vehicles once our thresholds have reached it's maximum. The smaller the number, the quicker we start to see vehicles despawn off in the background.
 
Through all of this, we see only mimimal difference yet still - we are now getting to the why of it all.
 
Next group of values are the vehicle spacing values. How can we spawn more traffic in when the spacing is SO far apart from each other? There are a total of 16 values for the base and maximum. I set them all to be the same per value(zone) so it's always the same. Each value represents an area of the GTA V map itself. Zones 0 - 6, and 8 - 14 are the spacing values for out in the countryside and the main interstates that drive through and around the countryside - everything happening from when we are heading towards Zancudo and beyond from the del perro area, all the way to the other side of the map - through Paleto Bay and on down to where we get off the exit ramps connecting back to Vinewood. Zones 7 and 15 are responsible for traffic throughout all urban areas of the city.
 
Notice how close the spacing is for zones 7 and 15? Obviously I want a LOT of traffic spawning!
 
<VehicleSpacing_Base>
<VehicleSpacing_0_Base value="70"/>
<VehicleSpacing_1_Base value="63"/>
<VehicleSpacing_2_Base value="52"/>
<VehicleSpacing_3_Base value="44"/>
<VehicleSpacing_4_Base value="45"/>
<VehicleSpacing_5_Base value="54"/>
<VehicleSpacing_6_Base value="53"/>
<VehicleSpacing_7_Base value="3"/>
<VehicleSpacing_8_Base value="33"/>
<VehicleSpacing_9_Base value="33"/>
<VehicleSpacing_10_Base value="33"/>
<VehicleSpacing_11_Base value="33"/>
<VehicleSpacing_12_Base value="33"/>
<VehicleSpacing_13_Base value="33"/>
<VehicleSpacing_14_Base value="33"/>
<VehicleSpacing_15_Base value="3"/>  
 
Finally we have the player road and non-player road densities. Obviously the further we push these values up, the more dense traffic will be within what ever we had set our inner radius values to as done from our above example. You can see they are far beyond the defaults! Notice I kepts the densities down in the first 6 zones, and then doubled up on it for the zones concerning inner-city areas?
 
</PlayerRoadDensityInc_Base>
<PlayerRoadDensityInc>
<PlayerRoadDensityInc_0 value="5"/>
<PlayerRoadDensityInc_1 value="5"/>
<PlayerRoadDensityInc_2 value="5"/>
<PlayerRoadDensityInc_3 value="5"/>
<PlayerRoadDensityInc_4 value="7"/>
<PlayerRoadDensityInc_5 value="7"/>
<PlayerRoadDensityInc_6 value="7"/>
<PlayerRoadDensityInc_7 value="30"/>
<PlayerRoadDensityInc_8 value="15"/>
<PlayerRoadDensityInc_9 value="15"/>
<PlayerRoadDensityInc_10 value="15"/>
<PlayerRoadDensityInc_11 value="15"/>
<PlayerRoadDensityInc_12 value="15"/>
<PlayerRoadDensityInc_13 value="15"/>
<PlayerRoadDensityInc_14 value="15"/>
<PlayerRoadDensityInc_15 value="30"/>

My Non-player side - 

<NonPlayerRoadDensityDec_Base>
<NonPlayerRoadDensityDec_0_Base value="7"/>
<NonPlayerRoadDensityDec_1_Base value="7"/>
<NonPlayerRoadDensityDec_2_Base value="7"/>
<NonPlayerRoadDensityDec_3_Base value="7"/>
<NonPlayerRoadDensityDec_4_Base value="7"/>
<NonPlayerRoadDensityDec_5_Base value="7"/>
<NonPlayerRoadDensityDec_6_Base value="7"/>
<NonPlayerRoadDensityDec_7_Base value="15"/>
<NonPlayerRoadDensityDec_8_Base value="15"/>
<NonPlayerRoadDensityDec_9_Base value="15"/>
<NonPlayerRoadDensityDec_10_Base value="15"/>
<NonPlayerRoadDensityDec_11_Base value="15"/>
<NonPlayerRoadDensityDec_12_Base value="15"/>
<NonPlayerRoadDensityDec_13_Base value="15"/>
<NonPlayerRoadDensityDec_14_Base value="15"/>
<NonPlayerRoadDensityDec_15_Base value="15"/>
 
Also, for performace sake, I brought down the vehicle population fram rates down a bit, because after all, we are asking a lot of the game-engine, LOL. You would really be surprise just how much traffic you can get in this game. Sometimes while driving through bumber-to-bumper traffic I can see expanding way out into the distance, I fear the game will choke, and it never ceases to amaze me just how well this game can cope with it with nary a hiccup.  
 
Done! If you have a PC as strong or stronger than my own, You can run with this without worry. If you have lesser of a PC, you still have room to increase traffic just not such extremes - but atleast now you know what to tinker with and how much, to get more very sorely needed traffic into your game. Kinda hard to have fun in a freakin' ghost town ya know? 
 
PC specs:

I7-4970k
16 Gb mem
nVidia 1070 FE
850 W PS

fake LOD traffic vehicles
In your gameconfig, push the below values WAY out -
<VehicleKeyholeShapeOuterRadius_Base value="150"/>
<VehicleKeyholeShapeOuterRadius value="175"/>
try raising both to like 500 or something
