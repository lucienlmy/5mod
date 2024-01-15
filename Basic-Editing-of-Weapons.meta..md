# **Introduction**
This is going to be a very basic guide on what *most of* the lines in weapons.meta do. I don't know what every single line does or what they mean but those are usually not important. Also, if you have any questions, corrections, etc please let me know. So let's start!

## What is weapons.meta?
Weapons.meta is the file that controls the game's "base" weapons. It is located in **update/update.rpf/common/data/ai**. Base weapons are GTA V's non-dlc weapons, these include:
```
WEAPON_UNARMED
WEAPON_KNIFE
WEAPON_KNIGHTSTICK
WEAPON_HAMMER
WEAPON_BAT
WEAPON_GOLFCLUB
WEAPON_CROWBAR
WEAPON_PISTOL
WEAPON_COMBATPISTOL
WEAPON_APPISTOL
WEAPON_PISTOL50
WEAPON_MICROSMG
WEAPON_SMG
WEAPON_ASSAULTSMG
WEAPON_ASSAULTRIFLE
WEAPON_CARBINERIFLE
WEAPON_ADVANCEDRIFLE
WEAPON_MG
WEAPOM_COMBATMG
WEAPON_PUMPSHOTGUN
WEAPON_SAWEDOFFSHOTGUN
WEAPON_BULLPUPSHOTGUN
WEAPON_STUNGUN
WEAPON_SNIPERRIFLE
WEAPON_HEAVYSNIPER
WEAPON_GRENADELAUNCHER
WEAPON_RPG
WEAPON_MINIGUN
```
Whether you are using "Notepad++" (recommended) or "OpenIV" you will search these names up to edit them. Let's start by editing a weapon.

# **WEAPON Editing**
First you are going to want to press "CTRL+F" and type in **WEAPON_(NAME)**. Note that it is not case sensitive. Once you have searched up **WEAPON_(NAME)** , you are going to be greeted by a huge wall of text. Now at first it may seem intimidating or confusing, but you will begin to see how self explanatory everything is. 

## **Damage**
We are going to start off with a very basic edit of the damage line. The damage line determines how many points the weapon will take away from NPCs. So, if you have searched up **WEAPON_(NAME)** you will see something like this:

```
<Damage value="26.000000" />
<DamageTime value="0.000000" />
<DamageTimeInVehicle value="0.000000" />
<DamageTimeInVehicleHeadShot value="0.000000" />
<HitLimbsDamageModifier value="0.500000" />
<NetworkHitLimbsDamageModifier value="0.800000" />
<LightlyArmouredDamageModifier value="0.750000" />
```
As you can see there are multiple damage types. The following table will explain what each one does. 

| Name     | Description |
| -----------      | ----------- |
| Damage      | When shooting NPC how much health to take away       |
| DamageTime | How long, in seconds, will the damage be taken away|
| DamageTimeInVehicle | How long, in seconds, will the damage be taken away inside of a vehicle|
| DamageTimeInVehicleHeadShot | How long, in seconds, will the damage be taken away inside of a vehicle (HeadShot)|
| HitLimbsDamageModifier | Damage modifier for arms and legs. (0 to disable these)|
| NetworkHitLimbsDamageModifier| Damage modifier for the player's arms and legs. |
| LightlyArmouredDamageModifier |Damage modifier for armored peds. (POLICE, SWAT, MERRYWEATHER, and ARMY) |

Now that you know what these damage lines do, feel free to edit them to your liking. The minimum value you can put is 0, and the maximum you can put is 999999. You will need to save the file, CTRL+S, for the changes to take effect. If you are using Notepad++ make sure you drag the file back into the location.

# **Bullet Force**
The bullet force is how much force is behind the bullet of the weapon you are editing. These lines are located directly under the damage lines. They will look like this:

```
<Force value="50.000000" />
<ForceHitPed value="125.000000" />
<ForceHitVehicle value="750.000000" />
<ForceHitFlyingHeli value="750.000000" />
```
The following table will explain what each of these lines do:

| Name      | Description |
| ----------- | ----------- |
| Force | This is the amount of "push" that will be applied to **objects**. (Benches, Lights, Glass, etc.)|
| ForceHitPed | This is the amount of "push" that will be applied to **NPCs.**|
| ForceHitVehicle | This is the amount of "push" applied to **cars** and **boats**|
| ForceHitFlyingHeli | This is the amount of "push" applied to **helicopters** and **planes**       |

You will also notice a block of text that is called "<OverrideForces>" this is used to edit the amount of force applied to the specific parts of NPCs. If you don't want to deal with this, you will need to delete it. To do so, start highlighting at  <OverrideForces> and finish highlighting at </OverrideForces>. Then you will want to press "Backspace". Delete any extra space between the above and below lines.  

# **Extra Bullet Edits**
Now that you understand how bullet force works, let's edit some more bullet values!

## 1. Penetration
Bullet penetration is how far and how much a bullet will go through an NPC or object. The line will look like this:
```
<Penetration value="0.010000" />
```
Be aware that this particular line is **very sensitive**. Edit this in very small increments or you will notice that bullets will go through 4-5 NPCs at a time!

## 2. Speed
Bullet speed is how fast a bullet will travel. The line will look like this:
```
<Speed value="2000.000000" />
```
I am not exactly sure what system it uses (metric or imperial) to calculate distance. When editing this I would not recommend to go under "500".

## 3. Batch Amount and Spread
**Batch Amount** is how many bullets are contained in a single shot. The line will look like this:

```
<BulletsInBatch value="1" />
```
You will mostly use this value when editing shotguns, but if you want a pistol to fire 5 bullets at a time, no one is stopping you. 

**Batch Spread** is how far the bullets are spread out.  The line will look like this:
```
<BatchSpread value="0.000000" />
```
For weapons that fire multiple bullets at a time, you will want to edit this very carefully as it sensitive. However, if you are editing a weapon that fires one bullet at a time, you will need to increase the value in big chunks.

# **Reload Time**
The reload time is how fast or long a gun will take to reload. There are 4 lines that control this and they look like this:
```
<ReloadTimeMP value="-1.000000" />
<ReloadTimeSP value="-1.000000" />
<VehicleReloadTime value="1.000000" />
<AnimReloadRate value="1.000000" />
```
The following table will explain what each line does:

| Name      | Description |
| ----------- | ----------- |
| ReloadTimeMP | The amount of time, in seconds, it takes to reload in multiplayer sessions (ignore)  |
| ReloadTimeSP| The amount of time, in seconds, it takes to reload in singleplayer (-1.000000 is default and is super fast)     |
| VehicleReloadTime | The amount of time, in seconds, it takes to reload inside all vehicles  |
| AnimReloadRate | How fast the reload animation will play.  |

So here is how these work. ReloadTime is what you will edit when you want to slightly decrease the reloading time. But, if you want to see significant changes, AnimReloadRate is what you want to edit. 

# **Weapon Effects**
The "<Fx>" section is full of fun and cool stuff edit. These range from muzzle flashes, tracers, environment flash, and barrel smoke. We are going to start off with simply editing tracers and muzzle flash. 

## 1. Muzzle Flash
In order to change muzzle flash you are going to need to know the name of each effect there is. Luckily, I am kind enough to put them all here for you.

```
muz_pistol_silencer
muz_assault_rifle
muz_stungun
muz_hunter
muz_buzzard
muz_alternate_star
muz_alternate_star_fp
muz_pistol
muz_pistol_fp
muz_rpg
muz_assault_rifle
muz_assault_rifle_fp
muz_tank
muz_minigun
muz_minigun_alt
muz_shotgun
muz_laser
muz_smg
muz_smg_fp
muz_railgun
muz_xm_thruster_mg
muz_clown
muz_xm_akula_mg_turret
muz_xm_barrage_minigun_turret
muz_xm_barrage_mg_turret
muz_xm_cherno
muz_xm_khanjali_mg
muz_xm_khanjali_railgun
muz_mounted_turret
muz_valkyrie
muz_valkyrie_turret
muz_xm_revolver
muz_musket_ng
```
In order to use these, you will need to edit these lines:
```
 <FlashFx></FlashFx>

 <FlashFxAlt></FlashFxAlt>

 <FlashFxFP></FlashFxFP>

 <FlashFxAltFP></FlashFxAltFP>
```
The following table will explain what each of these lines do:

| Name     | Description |
| ----------- | ----------- |
| FlashFx | Primary muzzle effect to use. (Third Person)      |
| FlashFxAlt | Alternative or Secondary muzzle effect to use. (Third Person)       |
| FlashFxFP | Primary  muzzle effect to use. (First Person)     |
| FlashFxAltFP | Alternative or Secondary muzzle effect to use. (First Person)        |

When using a muzzle effect such as, "muz_assault_rifle", you will want to paste the full name inside of the tags (><). Like this: 
```
<FlashFx>muz_assault_rifle</FlashFx>
<FlashFxAlt>muz_smg_fp</FlashFxAlt>
<FlashFxFP>muz_assault_rifle</FlashFxFP>
<FlashFxAltFP>muz_smg_fp</FlashFxAltFP>
```
Notice how I added a different muzzle effect for the alternative (FlashFxAlt) lines. Doing this can result in some really cool looking muzzle flash combos. But how can you edit the size and frequency of these muzzle effects? You can do these by editing these lines:

```
<FlashFxChanceSP value="1.000000" />
```
**FlashFxChanceSP** determines the frequency or how much the "<FlashFx(FP)>" muzzle effect will show.
```
<FlashFxAltChance value="0.200000" />
```
**FlashFxAltChance** determines the frequency or how much the "<FlashFxAlt(FP)>" muzzle effect will show.
```
<FlashFxScale value="1.000000" />
```
**FlashFxScale** determines the size of the muzzle effect.

## 2. Tracer Effects
Tracers are the lines that follow the bullets when you shoot. Basically, the orange or white glow that follows where you shoot. You can either remove or change these tracer effects. Here is the list of different tracer effects you can use:

```
bullet_tracer (default)
bullet_tracer_jet
bullet_tracer_turret
bullet_tracer_railgun
bullet_tracer_mg
bullet_tracer_valkyrie
```
These work the same as the muzzle effects only you will be editing a line that look like this:
```
<TracerFx></TracerFx>
```
Just like before you will input the tracer effect name in between the tags (><). It should like this:

```
<TracerFx>bullet_tracer_mg</TracerFx>
```
If you would like to **completely remove** tracers, you will want to make the line look like this:
```
<TracerFx />
```
# **Weapon Range**
Weapon range is the distance or how far a bullet will travel. The line you want to edit will look like this:
```
<WeaponRange value="120.000000" />
```
Again, I am not sure what system is used to calculate the distance so edit this file as much or as little as you want. There is no maximum number you can put, but if you want infinite range just put, "999999.000000".

# **Weapon Field of View**
The field of view when using a weapon is the part of the world that is visible through the camera. Basically it is how much you can see around you. The 2 lines that controls this look like this:
```
<CameraFov value="45.000000" />
<FirstPersonScopeFov value="30.00000"/>
<FirstPersonScopeAttachmentFov value="30.00000"/>
```
The following table will explain what each of these lines do:

| Name      | Description |
| ----------- | ----------- |
| CameraFov     | Camera's field of view when aiming in third person.       |
| FirstPersonScopeFov   | Camera's field of view when aiming in first person (Iron Sights)        |
| FirstPersonScopeAttachmentFov   | Camera's field of view when aiming in first person (Iron Sights + Attachment/Scope)        |

# **Conclusion**
That sums up the basics of editing weapons. As you could probably tell, I did not go over every single line inside of weapons.meta. This is because I don't know what everything does and others change very minute or unimportant things. I just wanted to covered the main features you will notice in game. I also did not include recoil editing as I am going to be saving this for the more advanced tutorial. I will also be explaining DLC weapons in another tutorial as they are located in different areas. If you have any specific questions or concerns feel free to ask me. I respond faster on discord: ¢няιѕρу#2374 .