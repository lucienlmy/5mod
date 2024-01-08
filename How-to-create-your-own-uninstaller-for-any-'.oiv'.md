There are multiple ways of doing this, but I'll quickly run through what is *probably* the easiest way for you to follow & for me to explain.

**Note:**
The big advantage to doing this manually yourself over using a mod author provided oiv uninstaller is that you can be sure that you reinstall the correct versions of the files for *your* game & no file information will be missing etc. 
If for example, the mod author provides older files that happen to have been updated with added information by a recent patch etc. Using their uninstaller, you will install the older version/s of the file/s & have information missing, which could lead to any & all kinds of issues depending on the file. 

This process will work whether you have installed the '**.oiv**' already of not. In fact, it's probably easier doing it *after* you have installed the original (less chance of getting mixed up between two copies of the '**.oiv**' & installing the wrong one etc).

**Instructions:**
 - Download & install [7zip](https://www.7-zip.org/download.html).
 - Right-click the '**.oiv**' & select '**7zip**' > '**Open archive**'.
 - Open the '**assembly.xml**' within the 7zip window.
 - Use the '**<content>**' section in '**assembly.xml**' to tell you the names of the files, their '**.oiv**' '**content**' folder (next to '**assembly.xml**')  location & where they are installed in-game.

**Example:**
```xml
<content> <!-- '<content>' section start  -->
<archive path="update\x64\dlcpacks\mpapartment\dlc.rpf" createIfNotExist="true" type="RPF7"> <!-- the path to the in-game '.rpf' archive the '.oiv' source files are installed into -->
<add source="mpapartment\x64\audio\config\dlcapartment_game.dat151.rel">\x64\audio\config\dlcapartment_game.dat151.rel</add> <!-- first folder path (in red here) is the '.oiv' 'content' folder file path of the source file to be installed. The second folder path (black) is the in-game folder path within/below the '.rpf' (outlined in '<archive path=' above) that the '.oiv' source file is to be installed to -->
</archive>
```

So for this example, the '**dlcapartment_game.dat151.rel**' file, located here within the '**.oiv**':

...\content\mpapartment\x64\audio\config\dlcapartment_game.dat151.rel

will be installed in-game here:

...update\x64\dlcpacks\mpapartment\dlc.rpf\x64\audio\config\dlcapartment_game.dat151.rel

 - Using the '**<content>**' section in '**assembly.xml**' as a guide, find a file in the 7zip folder structure.
 - Moving to [OpenIV](https://openiv.com/), use the **Ctrl+F3** search to search the vanilla game folder ('**Search area: Search in game folder only**' in OpenIV search box dropdown) for that *exact* file & open it's in-game location.
 - Using drag & drop, first drag the file out of OpenIV & onto the Desktop/a Windows folder & then drag it from there into 7zip overwriting the one in the '**.oiv**' by confirming the file copy dialog that appears.
 - After you have overwritten all the files, or just the files you want to return to vanilla, just close the 7zip window & then reinstall the new edited '**.oiv**' as you normally would.