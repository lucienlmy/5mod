[TheGanjaFarmer](https://web.archive.org/web/20230204223224/https://forums.gta5-mods.com/user/theganjafarmer) [4 years ago](https://web.archive.org/web/20230204223224/https://forums.gta5-mods.com/post/141740)

These are instructions for correcting first person aiming for replacement weapon mods.

There are many amazing replacement weapon mods on this site. However, many of them have incorrect first person aiming, down the iron sights as well as attachment scope sights.

Luckily, this is easily fixed with weapons.meta edits

This guide will teach you how to edit your weapons.meta files so you can fine tune any replacement weapon's first person aiming. I also will include a number of fixes for some of my favorite weapon replacements if you just want to install these and not fiddle with values.

First, a note about each weapon's meta location, since they are split between the vanilla weapons and all of the additional updates from Rockstar.

The vanilla weapons location is (mods)/update/update.rpf/common/data/ai)

This meta also controls the ammo type information for every weapon including dlc weapons. It is possible to edit ammo types to your preference (important for Pickups mod).

In the (mods)/update/update.rpf/common/data/ai) location you can also find the weaponcomponents.meta, which you can edit in order to change your vanilla gun magazine sizes, as well as the weaponanimations.meta, which controls the animations for each weapon (some cool things can be done in this meta with some trial and error).

You can edit in the main weapons.meta: (mods)/update/update.rpf/common/data/ai)

```
	Unarmed/vanilla melee weapons
	The pistol: 		WEAPON_PISTOL
	The combat pistol:      WEAPON_COMBATPISTOL
	The AP pistol:  	WEAPON_APPISTOL
	The .50 pistol:		WEAPON_PISTOL50
	The micro SMG:		WEAPON_MICROSMG
	The SMG: 		WEAPON_SMG
	The assault SMG:	WEAPON_ASSAULTSMG
	The assault rifle:	WEAPON_ASSAULTRIFLE
	The carbine rifle:	WEAPON_CARBINERIFLE
	The advanced rifle:     WEAPON_ADVANCEDRIFLE
	The machine gun:	WEAPON_MG
	The combat machine gun: WEAPON_COMBATMG
	The pump shotgun:	WEAPON_PUMPSHOTGUN
	The sawn off shotgun:	WEAPON_SAWNOFFSHOTGUN
	The bullpup shotgun:	WEAPON_BULLPUPSHOTGUN
	The assault shotgun:	WEAPON_ASSAULTSHOTGUN
	The sniper rifle:	WEAPON_SNIPERRIFLE
	The heavy sniper:	WEAPON_HEAVYSNIPER
	The grenade launcher:	WEAPON_GRENADELAUNCHER
	The RPG:		WEAPON_RPG
	Vanilla throwables and some others you may (probably not) want to edit
```

For DLC weapons:
You will find the dlc weapons metas in several locations.

The main location is: (mods)update/update.rpf/dlc_patch/**(dlc folder name)**/common/data/ai

**(dlc folder name)**: e.g. "mphipster"

this update/update.rpf location will override any other location, but sometimes the same meta has multiple locations. In this case, you only have to edit the one in this location.

Some guns' metas will not be in update/update.rpf, instead you will find them in:

(mods)/update/x64/dlcpacks/**(dlc folder name)**/common/data/ai

finally, for only a few melee weapons and some guns' weaponcomponents.metas, you will only find in:

(mods)/x64w.rpf/dlcpacks/ **(dlc folder name)** /dlc.rpf/common/data/ai

List of dlc guns and their respective meta locations (note: this is where they are originally, some weapons mods may add them all into update/update.rpf):

```
	WEAPON_REVOLVER:          (mods)update/update.rpf/dlc_patch/mpapartment/common/data/ai       ("weaponrevolver.meta")
	WEAPON_SNSPISTOL:         (mods)update/update.rpf/dlc_patch/mpbeach/common/data/ai           ("weaponsnspistol.meta")
	WEAPON_HEAVYPISTOL:       (mods)update/update.rpf/dlc_patch/mpbusiness/common/data/ai        ("weaponheavypistol.meta")
	WEAPON_SPECIALCARBINE:    (mods)update/update.rpf/dlc_patch/mpbusiness/common/data/ai        ("weaponspecialcarbine.meta")
	WEAPON_BULLPUPRIFLE:      (mods)update/update.rpf/dlc_patch/mpbusiness2/common/data/ai       ("weaponbullpuprifle.meta")
	WEAPON_HOMINGLAUNCHER:    (mods)update/update.rpf/dlc_patch/mpchristmas2/common/data/ai      ("weaponhominglauncher.meta")
	WEAPON_HEAVYSNIPER_MK2:   (mods)update/update.rpf/dlc_patch/mpgunrunning/common/data/ai      ("weapons_heavysniper_mk2.meta")
	WEAPON_FLASHLIGHT:        (mods)update/update.rpf/dlc_patch/mphalloween/common/data/ai       ("weaponflashlight.meta")
	WEAPON_VINTAGEPISTOL:     (mods)update/update.rpf/dlc_patch/mphipster/common/data/ai         ("weaponvintagepistol.meta")
	WEAPON_MUSKET:            (mods)update/update.rpf/dlc_patch/mpindependence/common/data/ai    ("weaponmusket.meta")
	WEAPON_FIREWORK:          (mods)update/update.rpf/dlc_patch/mpindependence/common/data/ai    ("weaponfirework.meta")
	WEAPON_MACHINEPISTOL:     (mods)update/update.rpf/dlc_patch/mplowrider/common/data/ai        ("weaponmachinepistol.meta")
	WEAPON_COMPACTRIFLE:      (mods)update/update.rpf/dlc_patch/mplowrider2/common/data/ai       ("weaponcompactrifle.meta")
	WEAPON_HEAVYSHOTGUN:      (mods)update/update.rpf/dlc_patch/mplts/common/data/ai             ("weaponheavyshotgun.meta")
	WEAPON_MARKSMANRIFLE:     (mods)update/update.rpf/dlc_patch/mplts/common/data/ai             ("weaponmarksmanrifle.meta")
	WEAPON_COMBATPDW:         (mods)update/update.rpf/dlc_patch/mpluxe/common/data/ai            ("weaponcombatpdw.meta")
	WEAPON_MARKSMANPISTOL:    (mods)update/update.rpf/dlc_patch/mpluxe2/common/data/ai           ("weaponmarksmanpistol.meta")
	WEAPON_GUSENBURG:         (mods)update/update.rpf/dlc_patch/mpvalentines/common/data/ai      ("weapongusenberg.meta")
	WEAPON_AUTOSHOTGUN:       (mods)update/x64/dlcpacks/mpbiker/dlc.rpf/common/data/ai           ("weaponautoshotgun.meta")
	WEAPON_MINISMG:           (mods)update/x64/dlcpacks/mpbiker/dlc.rpf/common/data/ai           ("weaponminismg.meta")
	WEAPON_COMPACTLAUNCHER:   (mods)update/x64/dlcpacks/mpbiker/dlc.rpf/common/data/ai           ("weaponcompactlauncher.meta")
	WEAPON_BULLPUPRIFLE_MK2:  (mods)update/x64/dlcpacks/mpchristmas2017/dlc.rpf/common/data/ai   ("weapons_bullpuprifle_mk2.meta")
	WEAPON_DOUBLEACTION:      (mods)update/x64/dlcpacks/mpchristmas2017/dlc.rpf/common/data/ai   ("weapons_doubleaction.meta")
	WEAPON_MARKSMANRIFLE_MK2: (mods)update/x64/dlcpacks/mpchristmas2017/dlc.rpf/common/data/ai   ("weapons_marksmanrifle_mk2.meta")
	WEAPON_PUMPSHOTGUN_MK2:   (mods)update/x64/dlcpacks/mpchristmas2017/dlc.rpf/common/data/ai   ("weapons_pumpshotgun_mk2.meta")
	WEAPON_REVOLVER_MK2:      (mods)update/x64/dlcpacks/mpchristmas2017/dlc.rpf/common/data/ai   ("weapons_revolver_mk2")
	WEAPON_SNSPISTOL_MK2:     (mods)update/x64/dlcpacks/mpchristmas2017/dlc.rpf/common/data/ai   ("weapons_snspistol_mk2.meta")
	WEAPON_SPECIALCARBINE_MK2:(mods)update/x64/dlcpacks/mpchristmas2017/dlc.rpf/common/data/ai   ("weapons_specialcarbine_mk2.meta")
	WEAPON_ASSAULTRIFLE_MK2:  (mods)update/x64/dlcpacks/mpgunrunning/dlc.rpf/common/data/ai      ("weapons_assaultrifle_mk2.meta")
	WEAPON_CARBINERIFLE_MK2:  (mods)update/x64/dlcpacks/mpgunrunning/dlc.rpf/common/data/ai      ("weapons_carbinerifle_mk2.meta")
	WEAPON_COMBATMG_MK2:      (mods)update/x64/dlcpacks/mpgunrunning/dlc.rpf/common/data/ai      ("weapons_combatmg_mk2.meta")
	WEAPON_PISTOL_MK2:        (mods)update/x64/dlcpacks/mpgunrunning/dlc.rpf/common/data/ai      ("weapons_pistol_mk2.meta")
	WEAPON_SMG_MK2:           (mods)update/x64/dlcpacks/mpgunrunning/dlc.rpf/common/data/ai      ("weapons_smg_mk2.meta")
	WEAPON_DBSHOTGUN:         (mods)update/x64/dlcpacks/mplowrider2/dlc.rpf/common/data/ai       ("weapondbshotgun.meta")
```

**Changing first person aiming for iron sights / scopes:**

Export the meta and make a backup at this point. You want to edit the metas with a program like notepad++. Control+F and search for the weapon that you want to edit, e.g. "WEAPON_PISTOL"

Then search or scroll down to the section where you see:

```
      <FirstPersonScopeOffset x="0.00000" y="0.0000" z="0.0000" />
      <FirstPersonScopeAttachmentOffset x="0.00000" y="0.0000" z="0.0000" />
      <FirstPersonScopeRotationOffset x="0.00000" y="0.0000" z="0.0000" />
      <FirstPersonScopeAttachmentRotationOffset x="0.00000" y="0.0000" z="0.0000" />
```

these are the values you want to edit.

To move your view forward, if the sights are too far away from the camera: increase the Y value of "FirstPersonScopeOffset" for iron sights, and the Y value of "FirstPersonScopeAttachmentOffset" for scopes. Decrease the Y value to move the camera away from the sights.
(Note: you generally want to change the value in increments of 0.00X or 0.000X, try changing the value (+/-)0.0005 to 0.006)

To move the sights down in your view, if the bullet impact is too low: decrease the Z value of "FirstPersonScopeOffset" for iron sights, and the Z value of "FirstPersonScopeAttachmentOffset" for scopes. Increase the Z value to move the sights up.
(Note: you generally want to change the value in increments of 0.00X or 0.000X, try changing the value (+/-)0.0005 to 0.008)

To move the gun left in your first person view: decrease the X value of "FirstPersonScopeOffset" for iron sights, and the X value of "FirstPersonScopeAttachmentOffset" for scopes. Increase the X value to move the gun to the right. (you wont need this for most guns)

To rotate the barrel of the gun downwards (and rotate the butt of the gun upwards), if the rear iron sight or scope is misaligned with the front sights of the gun: decrease the X value of "FirstPersonScopeRotationOffset" for iron sights, and the X value of "FirstPersonScopeAttachmentRotationOffset" for the scope. Increase the X value to rotate the barrel upwards. (You may need this to fine tune the rear sights so they are perfectly aligned with the front sights)
(Note: you generally want to change the value in increments of 0.X or 0.0X, the rotation offset is less sensitive than the normal offset. Try changing the value by (+/-)0.05 to 0.8, you may need to change it to >(+/-)1.0 in some cases)

To rotate the barrel of the gun to the right (and rotate the butt of the gun to the left), if the rear iron sight or scope is misaligned with the front sights of the gun: decrease the Z value of "FirstPersonScopeRotationOffset"for iron sights, and the Z value of "FirstPersonScopeAttachmentOffset" for scopes. Increase the Z value to rotate the barrel of the gun to the left. (You wont need this for most guns, though you might in order to fine tune the rear sights so they are perfectly aligned with the front sights)

My examples and tips and tricks:

First, always make backups of any file you are editing. It WILL save you major headaches if you screw something up. Do yourself a favor and make a folder where you lay everything out, including your backups and all your edited files.

Don't try to edit every weapon all at once. Go slowly and only edit one or a couple guns at the same time. You will eventually get a hang of it and will be able to estimate the values fairly accurately. Until then, expect to have to do a bunch of trial and error which means restarting your game/editing a bunch of times.

Edit the regular offset and get it dialed in before editing the rotation offset. The rotation offset will be effected by the regular offset position.

Here are examples of some weapons I have already fine tuned. The guns are bunched together when they share a common scope, you must install all of the replacement guns/scopes in the bundle if you want them all to have perfect aiming. If you aren't installing these, you can still take a look at the values I changed as a reference to get you started.

1) IMI mini Uzi + FN P90 + Kalashnikov AKM + Eotech Holographic sight

Download+install the gun/scope models into (mods)update/x64/dlcpacks/patchday8ng/dlc.rpf/x64/models/cdimages/weapons.rpf:

[@MAESTRE](https://web.archive.org/web/20230204223224/https://forums.gta5-mods.com/uid/326)'s IMI Mini Uzi ([https://www.gta5-mods.com/weapons/real-weapons-v-animated](https://web.archive.org/web/20230204223224/https://www.gta5-mods.com/weapons/real-weapons-v-animated))

[@MAESTRE](https://web.archive.org/web/20230204223224/https://forums.gta5-mods.com/uid/326)'s AKM ([https://www.gta5-mods.com/weapons/real-weapons-v-animated](https://web.archive.org/web/20230204223224/https://www.gta5-mods.com/weapons/real-weapons-v-animated))

[@Jridah](https://web.archive.org/web/20230204223224/https://forums.gta5-mods.com/uid/1098)'s FN P90 ([https://www.gta5-mods.com/weapons/jridah-s-redone-weapon-pack](https://web.archive.org/web/20230204223224/https://www.gta5-mods.com/weapons/jridah-s-redone-weapon-pack))

[@metroidguy](https://web.archive.org/web/20230204223224/https://forums.gta5-mods.com/uid/3252)'s eotech holographic sight* ([https://www.gta5-mods.com/weapons/weapon-attachments-pack](https://web.archive.org/web/20230204223224/https://www.gta5-mods.com/weapons/weapon-attachments-pack))
*You must rename "eotech" scope files: (w_at_scope_medium.ydr, w_at_scope_medium_hi.ydr, w_at_scope_medium.ytd) to "w_at_scope_macro.ydr", "w_at_scope_macro_hi.ydr", "w_at_scope_macro.ytd"

Copy and replace the lines below each weapon into ("weapons.meta") in (mods)update/update.rpf/common/data/ai

```
"WEAPON_MICROSMG":

      <FirstPersonScopeOffset x="0.000" y="-0.0400" z="-0.0060" />
      <FirstPersonScopeAttachmentOffset x="0.000" y="0.02500" z="-0.031" />
      <FirstPersonScopeRotationOffset x="0.0000" y="0.0000" z="0.450000" />


"WEAPON_ASSAULTSMG":

      <FirstPersonScopeOffset x="0.00200" y="0.0800" z="-0.01780" />
      <FirstPersonScopeAttachmentOffset x="0.00100" y="0.09000" z="-0.04800" />


"WEAPON_ASSAULTRIFLE":

      <FirstPersonScopeOffset x="0.00000" y="0.2750" z="0.0050" />
      <FirstPersonScopeAttachmentOffset x="0.00000" y="0.33000" z="-0.03200" />
      <FirstPersonScopeRotationOffset x="-0.03000" y="0.0000" z="0.0000" />
```

2) Colt M4A1 + H&K G36C + M249 + Aimpoint Red Dot scope

Download+install the gun/scope models into (mods)update/x64/dlcpacks/patchday8ng/dlc.rpf/x64/models/cdimages/weapons.rpf:

[@MAESTRE](https://web.archive.org/web/20230204223224/https://forums.gta5-mods.com/uid/326)'s H&K G36C: ([https://www.gta5-mods.com/weapons/real-weapons-v-animated](https://web.archive.org/web/20230204223224/https://www.gta5-mods.com/weapons/real-weapons-v-animated))

[@MAESTRE](https://web.archive.org/web/20230204223224/https://forums.gta5-mods.com/uid/326)'s Colt M4A1 (no attachments model): ([https://www.gta5-mods.com/weapons/real-weapons-v-animated](https://web.archive.org/web/20230204223224/https://www.gta5-mods.com/weapons/real-weapons-v-animated))

[@Jridah](https://web.archive.org/web/20230204223224/https://forums.gta5-mods.com/uid/1098)'s M249: ([https://www.gta5-mods.com/weapons/jridah-s-redone-weapon-pack](https://web.archive.org/web/20230204223224/https://www.gta5-mods.com/weapons/jridah-s-redone-weapon-pack))

[@metroidguy](https://web.archive.org/web/20230204223224/https://forums.gta5-mods.com/uid/3252)'s Aimpoint red dot scope: ([https://www.gta5-mods.com/weapons/weapon-attachments-pack](https://web.archive.org/web/20230204223224/https://www.gta5-mods.com/weapons/weapon-attachments-pack))

Copy and replace the lines below each weapon into ("weapons.meta") in (mods)update/update.rpf/common/data/ai

```
"WEAPON_CARBINERIFLE":

      <FirstPersonScopeOffset x="0.00000" y="-0.0200" z="-0.0230" />
      <FirstPersonScopeAttachmentOffset x="0.00000" y="0.125000" z="-0.0292" />

"WEAPON_COMBATMG":

      <FirstPersonScopeOffset x="0.00275" y="0.0750" z="-0.0280" />
      <FirstPersonScopeAttachmentOffset x="0.00300" y="0.0900" z="-0.0560" />
      <FirstPersonScopeRotationOffset x="-0.63000" y="0.0000" z="0.0000" />
```

Copy and replace the lines below into ("weaponspecialcarbine.meta") in (mods)update/update.rpf/dlc_patch/mpbusiness/common/data/ai

```
"WEAPON_SPECIALCARBINE":

      <FirstPersonScopeOffset x="0.000000" y="0.000000" z="-0.042100" />
      <FirstPersonScopeAttachmentOffset x="0.000000" y="0.125000" z="-0.071050" />
      <FirstPersonScopeRotationOffset x="-1.770000" y="0.000000" z="0.000000" />
```

3) Several sample pistol edits (install whichever you like):

[@MAESTRE](https://web.archive.org/web/20230204223224/https://forums.gta5-mods.com/uid/326)'s Beretta M9: ([https://www.gta5-mods.com/weapons/real-weapons-v-animated](https://web.archive.org/web/20230204223224/https://www.gta5-mods.com/weapons/real-weapons-v-animated))

Copy and replace the line into ("weapons.meta") in (mods)update/update.rpf/common/data/ai

```
"WEAPON_PISTOL":

      <FirstPersonScopeOffset x="0.00000" y="0.0000" z="-0.0010" />
```

[@Jridah](https://web.archive.org/web/20230204223224/https://forums.gta5-mods.com/uid/1098)'s Glock 17: ([https://www.gta5-mods.com/weapons/jridah-s-redone-weapon-pack](https://web.archive.org/web/20230204223224/https://www.gta5-mods.com/weapons/jridah-s-redone-weapon-pack))

Copy and replace the line into ("weapons.meta") in (mods)update/update.rpf/common/data/ai

```
"WEAPON_COMBATPISTOL":

      <FirstPersonScopeOffset x="-0.00200" y="0.0000" z="0.0040" />
```

[@Jridah](https://web.archive.org/web/20230204223224/https://forums.gta5-mods.com/uid/1098)'s Glock 20: ([https://www.gta5-mods.com/weapons/jridah-s-redone-weapon-pack](https://web.archive.org/web/20230204223224/https://www.gta5-mods.com/weapons/jridah-s-redone-weapon-pack))

Copy and replace the line into ("weapons.meta") in (mods)update/update.rpf/common/data/ai

```
"WEAPON_APPISTOL":

      <FirstPersonScopeOffset x="0.00000" y="0.0000" z="0.0070" />
```

[@Jridah](https://web.archive.org/web/20230204223224/https://forums.gta5-mods.com/uid/1098)'s Desert Eagle: ([https://www.gta5-mods.com/weapons/jridah-s-redone-weapon-pack](https://web.archive.org/web/20230204223224/https://www.gta5-mods.com/weapons/jridah-s-redone-weapon-pack))

Copy and replace the lines into ("weapons.meta") in (mods)update/update.rpf/common/data/ai

```
"WEAPON_PISTOL50":

      <FirstPersonScopeOffset x="0.00100" y="0.0000" z="-0.0158" />
      <FirstPersonScopeAttachmentOffset x="0.00000" y="0.00000" z="0.00000" />
      <FirstPersonScopeRotationOffset x="0.55000" y="0.0000" z="0.0000" />
```

Hope this helps some people, I know it has been requested a lot. Let me know if something isn't clear or you are confused with any of the steps. Also feel free to post any fixes you make for any other weapon replacement in the thread, might be helpful to some people.

[Original post by TheGanjaFarmer](https://web.archive.org/web/20230204223224/https://forums.gta5-mods.com/topic/23704/tutorial-correcting-first-person-aiming-for-replacement-weapon-mods-detailed-meta-edit-intructions)