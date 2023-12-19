Original post by [a63nt-5m1th](https://forums.gta5-mods.com/user/a63nt-5m1th) at GTA5-Mods.com

***


Essentially pretty simple this, just a little time needed to configure & find the correct brightness/exposure value/s to use, but ***guaranteed* to work** & **disable eye adaptation *completely***. Like ***completely*** disable it, ***zero***, ***none***, ***nada***, ***off***, ***gone***, ***bye***, ***dead***  :thumbsup:

Method:
-
Basically, the '**<postfx_exposure_min>**' & '**<postfx_exposure_max>**' values in the **timecycle** files ('**w_clear.xml**', '**w_extrasunny.xml**', ... etc) control the range of brightness/darkness Adaptation is able to use. So setting them to the same value (*whatever* that value may be) for any given time of day, *completely* disables Adaptation's ability to change the brightness of the screen for that particular time of day.

**Example** (Adaptation disabled throughout all (13) different times of day)**:**
```xml
<!--            Time of Day           0      5      6      7      8      9      13     17     18     19     20     21     22 -->
		<postfx_exposure_min> 3.8500 0.5000 0.5500 0.5700 0.5800 0.5900 0.6000 0.5800 0.5700 0.5600 0.5500 0.5400 3.8500</postfx_exposure_min>
		<postfx_exposure_max> 3.8500 0.5000 0.5500 0.5700 0.5800 0.5900 0.6000 0.5800 0.5700 0.5600 0.5500 0.5400 3.8500</postfx_exposure_max>
```
**Key Points:**
-
**To Disable Adaptation:**
 - All that matters is that the values for '**<postfx_exposure_min>**' & '**<postfx_exposure_max>**' be the same for any given time of day. 

**For Brightness Tweaking/Recreating a Timecycle Look:**
 - The higher you set the '**<postfx_exposure_min>**' & '**<postfx_exposure_max>**' value the brighter the screen will be.  
 - The lower you set them (can be negative *if* required) the darker the screen will be. 


**Note:**
The *exact* value/s that *you* use for '**<postfx_exposure_min>**' & '**<postfx_exposure_max>**' for any given time of day, will be *specific* to *your* game & visual setup. Copying my example values above will *likely* result in a screen that is too bright or too dark to be ideal. You could *perhaps* use those values as a starting point, or as a quick test to confirm this method works, but ultimately, you'll have to find your own value/s that work for you. :thumbsup:


Screenshots - Before & After Comparison:
-
As you can see from these screenshots, once you find the right value/s (for *your* game), it's entirely possible to get your weather looking *nigh on identical* to how it was before:

**ExSunny - Day (Before):**

![ExSunny - Day (Before)](https://live.staticflickr.com/65535/52774570757_056e777e05_o.jpg)

**ExSunny - Day (After):**

![ExSunny - Day (After)](https://live.staticflickr.com/65535/52775587903_a913af16a0_o.jpg)

Slider comparison of above **Day** images [here](https://imgsli.com/MTY1MjI1).

**ExSunny - Night (Before):**

![ExSunny - Night (Before)](https://live.staticflickr.com/65535/52775104941_614cc893bd_o.jpg)

**ExSunny - Night (After):**

![ExSunny - Night (After)](https://live.staticflickr.com/65535/52774570262_b37f6ec764_o.jpg)

Slider comparison of above **Night** images [here](https://imgsli.com/MTY1MjM4).

**Note:**
For the comparisons above I only used minimum increments of 0.0100 to find a brightness *close* to what I had before. Obviously, it's entirely possible to edit in smaller increments for a more *exact* result/match. Doing so, I'm pretty confident it would be possible to recreate a *truly identical* look. 

So, in short, using this method, it's *entirely* possible to re-create a timecycle look that's indistinguishable from the original, while also ***completely 100% disabling adaptation*** at the same time. :thumbsup: