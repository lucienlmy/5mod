Just covering the most common '**dlclist.xml**' errors that can cause ***all your dlc*** to stop working/loading & also some guidelines on formatting & avoiding syntax errors.

**Note:** Reference to capital ('I') or lowercase ('i') apply ***only*** to the **<Item>/~/</item>** parts of the lines. *Not* to the dlc name or anything else.

**No DLC is loading:**
If *all* your dlc has suddenly stopped loading, the most common cause is that there is a line in your '**dlclist.xml**' that starts with a capital 'I' in the '**<Item>**' part & ends with a lowercase 'i' in the '**</Item>**' *or vice versa* (<item>/dlc-name-here/</Item> etc).

**Capital ('<Item>')/Lowercase ('<item>'):**

**Both of these will work:**
```xml
		<Item>dlcpacks:/mpxmas_604490/</Item>
```
```xml
		<item>dlcpacks:/mpchristmas2/</item>
```
You can have *different* lines, some with two capital 'I's ('**<Item>**' & '**</Item>**'), some with two lowercase 'i's ('**<item>**' & '**</item>**'). That's totally fine. They will both work. :thumbsup:

**Example** (all your dlc will load perfectly fine if formatted something like this)**:**
```xml
		<item>platform:\dlcPacks\mpBeach\</item>
		<Item>platform:\dlcPacks\mpBusiness\</Item>
		<item>platform:\dlcPacks\mpChristmas\</item>
		<item>platform:\dlcPacks\mpValentines\</item>
		<Item>platform:\dlcPacks\mpBusiness2\</Item>
		<Item>platform:\dlcPacks\mpHipster\</Item>
		<Item>platform:\dlcPacks\mpIndependence\</Item>
		<item>platform:\dlcPacks\mpPilot\</item>
		<item>platform:\dlcPacks\spUpgrade\</item>
		<Item>platform:\dlcPacks\mpLTS\</Item>
```
Just make sure ***not*** to mix & match capitals 'I's ('**<Item>**' or '**</Item>**') & lowercase 'i's ('**<item>**' or '**</item>**') ***within the same line*** (see below).

**Any one or more lines like this, will break 'dlclist.xml' functionality & *STOP ALL DLC* from loading:**
```xml
		<item>dlcpacks:/mpxmas_604490/</Item>
```
```xml
		<Item>dlcpacks:/mpchristmas2/</item>
```
**Example** (some of these lines will cause your game to not load *any* dlc)**:**
```xml
		<item>platform:\dlcPacks\mpBeach\</Item> (bad)
		<Item>platform:\dlcPacks\mpBusiness\</item> (bad)
		<item>platform:\dlcPacks\mpChristmas\</item> (good)
		<Item>platform:\dlcPacks\mpValentines\</item> (bad)
		<Item>platform:\dlcPacks\mpBusiness2\</Item> (good)
		<item>platform:\dlcPacks\mpHipster\</Item> (bad)
		<Item>platform:\dlcPacks\mpIndependence\</Item> (good)
		<item>platform:\dlcPacks\mpPilot\</item> (good)
		<item>platform:\dlcPacks\spUpgrade\</Item> (bad)
		<Item>platform:\dlcPacks\mpLTS\</Item> (good)
```

**Easy way to find syntax errors:**
If you use '**Edit**' (right-click file>'**Edit**' or '**Ctrl+Enter**') to open a file using [OpenIV](https://openiv.com/), a  '**[</> XML]**' button will appear at the top when you are *in* the file. Tap that button & OpenIV will check the file for syntax errors & take you to where it thinks the error is if it finds one. After you fix the error, hit the '**[</> XML]**' button again to check there isn't more than one & then '**[Save]**' the file (bottom right).  :thumbsup:
**Note:** OpenIV will now also notify you of syntax errors when you attempt to '**[Save]**' a file after editing it.

**Backslashes or Forwardslashes on either side of the dlc name:**
These don't matter, in that they can be backslashes (' \ ') OR forwardslashes (' / ') & even if you mix & match in the same line, the dlc will still load perfectly fine.

**Example** (all this dlc will still load perfectly, even if formatted like this)**:**
```xml
		<Item>dlcpacks:/forest/</Item>
		<Item>dlcpacks:\firebird77/</Item>
		<item>dlcpacks:\na1\</item>
		<item>dlcpacks:/16challenger\</item>
```

**Correct general formatting of 'dlclist.xml' file & where to add new lines:**

If you're new to GTAV modding, it's not always clear in mod instructions where *exactly* one should add the dlc line, so just to clarify, it can go *anywhere* below '**<Paths>**' but above '**</Paths>**' & in it's own line is *usually* best/easiest to read etc.
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SMandatoryPacksData>
	<Paths>
Add DLC Lines HERE (below what already exists is usually best, but anywhere here, in it's own line, will work)
	</Paths>
</SMandatoryPacksData>
```

**Example:**
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SMandatoryPacksData>
	<Paths>
		...~
		<Item>dlcpacks:/forest/</Item>
		<Item>dlcpacks:/firebird77/</Item>
		<item>dlcpacks:\na1\</item>
		<item>dlcpacks:\16challenger\</item>
		<Item>dlcpacks:\zmissile\</Item>
		<Item>dlcpacks:\dov\</Item>
		<Item>dlcpacks:\satoca\</Item>
		<Item>dlcpacks:\gto2\</Item>
		Adding a new line in here is usually easiest
	</Paths>
</SMandatoryPacksData>
```
That's the basics coverered I think :thinking: but if you find any other common '**dlclist.xml**' issues I've forgotten to mention, give me a shout & I'll add them :thumbsup: