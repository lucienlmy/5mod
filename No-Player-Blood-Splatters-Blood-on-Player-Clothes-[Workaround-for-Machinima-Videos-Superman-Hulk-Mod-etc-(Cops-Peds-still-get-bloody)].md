I'm aware this will be niche but there's a few out there that have been looking for some way of doing this for many years so I thought I'd post it :thumbsup:

It's a pretty effective & reasonably versatile workaround for those of you that don't want blood splatters or blood soaked clothes on your player when he/she gets shot while still leaving the cops covered in the red stuff when they get hit by bullets. Perfect for staged Superman/Hulk/Terminator Machinima videos & the like.

Have a look through '**loadouts.meta**' & make a note of all the guns the cops/enemies you plan to fight use.
For me it was these:

	WEAPON_PISTOL
	
	WEAPON_PUMPSHOTGUN
	
	WEAPON_SMG
	
	WEAPON_CARBINERIFLE
	
	WEAPON_MICROSMG

**Note:** Depending on how you have the cops/swat/enemies etc armed there may be more so you'll have to hunt for them, possibly in other weapon meta files. 

All those ones named above are in the '**weapons.meta**' here anyway:

...\mods\update\update.rpf\common\data\ai\weapons.meta

Open up the file & set all of the damages to zero for the weapons you noted earlier:
```xml
          <Damage value="0.000000" />
```
That's it. Done. No blood will show when those weapons are used to shoot anyone. :thumbsup:

The only real downsides to doing it like this are:

 - **A )-** Your enemies will be unable to kill the player with those weapons.

 - **B )-** Your player can't use any of the guns the cops/swat etc use or if you do you won't be able to kill anyone with them & no blood will show when you shoot someone with them. Your enemies will ragdoll, but they won't die. All other weapons will work as normal (blood, death etc).
 - **C )-** When the cops are shooting your player he/she will twitch slightly when hit (looks kinda cool actually, very Terminator 2).

**Possible Solution for A )- :**
One possibility here (if you did want your player to eventually die) would be to leave 5 star dispatch peds with weapons that could kill the player. Could make for some epic Ned Kelly style last stand videos. 

**Possible Solution for B )- :**
The cop etc weapons are not the most vital of weapons anyway (plenty alternatives) but if you did want to use them against the cops it would be easy enough to create new cop specific versions of them with zero damage in the meta files (COP_WEAPON_PISTOL etc) & then assign them to the cops in '**loadouts.meta**', leaving you free to use the default versions for your player as normal.  :thumbsup:

**Possible Solution for C )- :**
I didn't test this but I'm sure reducing the '**<Force value**' to zero in the weapon's meta file will get rid of the twitch when the player is shot (or alternatively, raise it if you want more twitch):
```xml
          <Force value="0.000000" />
```

Hope this helps somebody out anyway. All the best :thumbsup: