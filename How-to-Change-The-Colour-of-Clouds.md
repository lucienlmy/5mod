The original post was by [a63nt-5m1th](https://www.gta5-mods.com/users/a63nt-5m1th) on the 5mods forums.

***

Been a while, but this should help :thumbsup:

Finding the right cloud settings to edit:

The names of the cloud settings in 'cloudkeyframes.xml' correlate with the 'CloudSettingsName' lines for each weather/timecycle in 'weather.xml'

Example:

**cloudkeyframes.xml:** 
```xml
	<Item> 
	  <Name>CONTRAILSclouds</Name>
	  <Settings>
		<CloudList>
		  <mProbability content="int_array">
```

**weather.xml:**
```xml
	<CloudSettingsName>CONTRAILSclouds</CloudSettingsName>
```

**Editing Cloud Colours in 'cloudkeyframes.xml':**

To change the colours, edit these sections (**'CloudColor'** (colour correction), **'CloudAmbientColor'** (overall colour), **'CloudSkyColor'** (uplighting) & **'CloudBounceColor'** (downlighting))

For the most part, with my own edits, I've pretty much stuck to editing **'CloudSkyColor'** & **'CloudBounceColor'** to get what I want, but experiment with **'CloudColor'** & **'CloudAmbientColor'** if you like, mainly so you're not restricted by my limited editing knowledge of them :thumbsup:

```xml
		<CloudColor>
		  <keyData>
			<numKeyEntries value="14" />
			<keyEntryData content="float_array"> <!-- COLOUR CORRECTION -->
			  0.000000	1.000000	1.000000	1.000000	1.000000
			  4.000000	1.000000	1.000000	1.000000	1.000000
			  5.000000	1.000000	1.000000	1.000000	1.000000
			  6.000000	1.000000	1.000000	1.000000	1.000000
			  7.000000	0.500000	0.500000	0.500000	1.000000
			  8.000000	0.500000	0.500000	0.500000	1.000000
			  12.000000	0.500000	0.500000	0.500000	1.000000
			  16.000000	0.500000	0.500000	0.500000	1.000000
			  17.000000	0.500000	0.500000	0.500000	1.000000
			  18.000000	0.500000	0.500000	0.500000	1.000000
			  19.000000	0.500000	0.500000	0.500000	1.000000
			  20.000000	0.500000	0.500000	0.500000	1.000000
			  21.000000	0.600000	0.600000	0.600000	1.000000
			  22.000000	1.000000	1.000000	1.000000	1.000000
			</keyEntryData>
		  </keyData>
		</CloudColor>
.......................................... ...
		<CloudAmbientColor>
		  <keyData>
			<numKeyEntries value="14" />
			<keyEntryData content="float_array"> <!-- OVERALL COLOUR -->
			  0.000000	0.000000	0.000000	0.000000	1.000000
			  4.000000	0.000000	0.000000	0.000000	1.000000
			  5.000000	0.000000	0.000000	0.000000	1.000000
			  6.000000	0.000000	0.000000	0.000000	1.000000
			  7.000000	0.000000	0.000000	0.000000	1.000000
			  8.000000	0.000000	0.000000	0.000000	1.000000
			  12.000000	0.000000	0.000000	0.000000	1.000000
			  16.000000	0.000000	0.000000	0.000000	1.000000
			  17.000000	0.000000	0.000000	0.000000	1.000000
			  18.000000	0.000000	0.000000	0.000000	1.000000
			  19.000000	0.000000	0.000000	0.000000	1.000000
			  20.000000	0.000000	0.000000	0.000000	1.000000
			  21.000000	0.000000	0.000000	0.000000	1.000000
			  22.000000	0.000000	0.000000	0.000000	1.000000
			</keyEntryData>
		  </keyData>
		</CloudAmbientColor>
.......................................... ...
		<CloudSkyColor>
		  <keyData>
			<numKeyEntries value="14" />
			<keyEntryData content="float_array"> <!-- UP LIGHT -->
			  0.000000	0.020000	0.030000	0.040000	1.000000
			  4.000000	0.025000	0.035000	0.040000	1.000000
			  5.000000	0.180000	0.190000	0.200000	1.000000
			  6.000000	0.220000	0.410000	0.600000	1.000000
			  7.000000	0.800000	0.770000	0.750000	1.000000
			  8.000000	0.800000	0.800000	0.800000	1.000000
			  12.000000	0.800000	0.800000	0.800000	1.000000
			  16.000000	0.800000	0.800000	0.800000	1.000000
			  17.000000	0.800000	0.800000	0.800000	1.000000
			  18.000000	0.800000	0.800000	0.800000	1.000000
			  19.000000	0.800000	0.770000	0.750000	1.000000
			  20.000000	0.290000	0.380000	0.460000	1.000000
			  21.000000	0.150000	0.170000	0.180000	1.000000
			  22.000000	0.020000	0.030000	0.040000	1.000000
			</keyEntryData>
		  </keyData>
		</CloudSkyColor>
		<CloudBounceColor>
		  <keyData>
			<numKeyEntries value="14" />
			<keyEntryData content="float_array"> <!-- DOWN LIGHT -->
			  0.000000	0.020000	0.017000	0.015000	1.000000
			  4.000000	0.020000	0.017000	0.015000	1.000000
			  5.000000	0.110000	0.120000	0.130000	1.000000
			  6.000000	0.130000	0.150000	0.210000	1.000000
			  7.000000	0.190000	0.200000	0.210000	1.000000
			  8.000000	0.200000	0.210000	0.230000	1.000000
			  12.000000	0.200000	0.210000	0.230000	1.000000
			  16.000000	0.200000	0.210000	0.230000	1.000000
			  17.000000	0.200000	0.210000	0.230000	1.000000
			  18.000000	0.200000	0.210000	0.230000	1.000000
			  19.000000	0.220000	0.210000	0.200000	1.000000
			  20.000000	0.180000	0.180000	0.185000	1.000000
			  21.000000	0.110000	0.120000	0.130000	1.000000
			  22.000000	0.020000	0.017000	0.015000	1.000000
			</keyEntryData>
		  </keyData>
		</CloudBounceColor>
```
* The first column on the far left is **Time of Day**
* The second column from left is **Red**
* Third is **Green**
* Fourth is **Blue**
* Far right is probably alpha/saturation or something (I've pretty much left it as is, but experiment if you want).
According to the info I have (untested by me), the **'CloudLightColor'** sections _**do not work**_ & the sections **'CloudEastColor'**, **'CloudWestColor'** & **'CloudScaleFillColors'** are marked as _**'Do not touch**_' for some reason.