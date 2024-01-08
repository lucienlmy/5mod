![alt text](https://i.imgur.com/aRHi7b7.jpg)

Open **timecycle_mods_4.xml** (**update/update.rpf/common/data/timecycle**) and search for **phone_cam1**. Remove all the values and then paste these ones:
```
    <postfx_desaturation>0.750 0.000</postfx_desaturation>
    <postfx_noise>0.000 0.000</postfx_noise>
    <postfx_vignetting_intensity>0.975 0.000</postfx_vignetting_intensity>
    <postfx_vignetting_radius>10.000 0.000</postfx_vignetting_radius>
    <postfx_vignetting_contrast>0.250 0.000</postfx_vignetting_contrast>
    <postfx_vignetting_col_r>0.024 0.000</postfx_vignetting_col_r>
    <postfx_vignetting_col_g>0.035 0.000</postfx_vignetting_col_g>
    <postfx_vignetting_col_b>0.047 0.000</postfx_vignetting_col_b>
    <postfx_scanlineintensity>0.100 0.000</postfx_scanlineintensity>
```
Also change **numMods** from 39 to 9.
Note: you still need to toggle the filter (the first one).