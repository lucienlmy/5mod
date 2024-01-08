**Backup:**
As with anything modding related, make backups of everything you intend to edit first.
For GTA V, I wholeheartedly recommend backing up the entire '**.rpf**' archive, not just the files you are editing. 
That has got me out of a few tight spots over the years & can mitigate the task of having to reinstall *every* edited file to a '**.rpf**' if things go wrong. :thumbsup:

**HOW TO REMOVE EXTRAS FROM VEHICLES:**

**Basic Procedure:**

 - Export vehicle's '**.yft**' & '**_hi.yft**' to '**.yft.xml**' using Codewalker's RPF Explorer.
 - Edit '**.yft.xml**' files using text editor & reduce scale of selected extras to zero to stop them from appearing in-game.
 - Import vehicle's  '**.yft.xml**'s back into the game using Codewalker's RPF Explorer.


**Detailed Procedure:**

**Make a note of what extras you want to remove:**
 - Boot up the game, spawn the vehicle & using a [trainer](https://www.gta5-mods.com/all/tags/trainer/most-downloaded) make a note of what extras you do not want to appear.
 - They are numbered the same in the files as they are in [ENT](https://www.gta5-mods.com/scripts/enhanced-native-trainer-zemanez-and-others) anyway, so figure most trainers will be the same.

**Export vehicle '.yft' to '.yft.xml' using Codewalker:**
 - Grab yourself a copy of CodeWalker from the [CodeWalker discord](https://discord.com/invite/BxfKHkk) (**Note:** Codewalker v.29 on gta-mods is out of date & lacks necessary features, always get the latest version of CodeWalker from it's Discord :thumbsup:)
 - Once you have a copy of CodeWalker load up it's '**RPF Explorer**' (either, **CodeWalker** > '**[<<]**' button (top right) > '**[Tools]**' > '**RPF Explorer...**' or in new versions you can find the '**CodeWalker RPF Explorer.exe**' in Codewalker's install folder & load it on it's own from there).
 - In '**CodeWalker RPF Explorer**' track to the location of the vehicle you want to remove extra's from.
 - Once there, highlight the vehicle's '**.yft**' by left clicking on it & then use '**Ctrl+left-click**' to also highlight it's '**_hi.yft**'. 
 - With both files selected/highlighted, right-click & select '**Export XML...**'. 
 - Select a location for the exported '**.yft.xml**'s & hit '**[OK]**'

**Edit '.yft.xml' using a Text Editor (like Notepad++ etc):**
 - Track to the '**.yft.xml**' export location & open them with your text editor of choice
 - Search for '**extra**' in the '**.yft.xml**'s & near the top you will find sections like this for each of the extras:

**Example:**
```xml
    <Item>
     <Name>extra_8</Name>
     <Tag value="8881" />
     <Index value="11" />
     <ParentIndex value="0" />
     <SiblingIndex value="12" />
     <Flags>RotX, RotY, RotZ, TransX, TransY, TransZ</Flags>
     <Translation x="2.273737E-13" y="-1.966892" z="-0.1955207" />
     <Rotation x="0" y="2.710494E-20" z="-2.842159E-14" w="1" />
     <Scale x="1" y="1" z="1" /> 
     <TransformUnk x="0" y="4" z="-3" w="0" />
    </Item>
```
 - Using their numbering as a guide, find the extra/s you want to remove, & then simply set the x, y & z values in their '**<Scale**' line to zero.

**Example:**
```xml
    <Item>
     <Name>extra_8</Name>
     <Tag value="8881" />
     <Index value="11" />
     <ParentIndex value="0" />
     <SiblingIndex value="12" />
     <Flags>RotX, RotY, RotZ, TransX, TransY, TransZ</Flags>
     <Translation x="2.273737E-13" y="-1.966892" z="-0.1955207" />
     <Rotation x="0" y="2.710494E-20" z="-2.842159E-14" w="1" />
     <Scale x="0" y="0" z="0" /> <!-- set x, y & z to zero -->
     <TransformUnk x="0" y="4" z="-3" w="0" />
    </Item>
```

 - Save the file/s & head back to Codewalker's RPF Explorer

**Importing edited '.yft.xml''s back into the game:** 
 - In CW's RPF Explorer, hit the '**[:shield:Edit mode]**' button (top right-ish) & accept any warnings by hitting '**[Yes]**'
 - Right-click anywhere in the folder (the folder where you got the original '**.yft**' from obvs) & select '**Import XML...**'
 - Track to the location of your edited '**.yft.xml**' files, select them both & hit '**[Open]**'
 - Codewalker will take a few seconds to import the files, wait for it to complete & then close the '**RPF Explorer**' window.

That's it, those extra's, although still _technically_ there in the '**.yft**', should not appear in game. 

Combine this with the info in my previous post on [How to make specific vehicle EXTRAS appear on a vehicle EVERY spawn](https://forums.gta5-mods.com/topic/19786/tutorial-how-to-make-specific-vehicle-extras-appear-on-a-vehicle-every-spawn) & you will have *pretty much* complete control over what combination of extras appear or do not appear in any given vehicle spawn.

Any questions/issues, give me a shout :thumbsup: