@Kubanetz 

'**blizzard_render_drop.xml**'

Use **Ctrl+F3** in OpenIV to search your '**mods**' folder to find it/them (usually in '**common.rpf**', or sometimes '**update.rpf**' (if moved etc). Edit the one in '**update.rpf**' *if* it exists. If not, edit the one in '**common.rpf**' :thumbsup:

**Vanilla one looks like this inside:**

```xml
<?xml version="1.0" encoding="UTF-8"?>

<rage__ptxgpuDropRenderSettings>
  <textureRowsColsStartEnd x="2.000000" y="2.000000" z="0.000000" w="3.000000" />
  <textureAnimRateScaleOverLifeStart2End2 x="0.000000" y="0.000000" z="0.000000" w="3.000000" />
  <sizeMinMax x="0.025000" y="0.025000" z="0.035000" w="0.035000" />
  <colour x="1.000000" y="1.000000" z="1.000000" w="1.000000" />
  <fadeInOut x="1.000000" y="1.000000" />
  <fadeNearFar x="1.000000" y="100.000000" />
  <fadeGrdOffLoHi x="0.000000" y="-15.000000" z="0.500000" w="100.000000" />
  <rotSpeedMinMax x="-5.000000" y="5.000000" />
  <directionalZOffsetMinMax x="-0.000000" y="0.000000" z="0.000000" />
  <dirVelAddCamSpeedMinMaxMult x="0.000000" y="0.000000" z="0.000000" />
  <edgeSoftness value="1.000000" />
  <particleColorPercentage value="1.000000" />
  <backgroundDistortionVisibilityPercentage value="0.000000" />
  <backgroundDistortionAlphaBooster value="1.000000" />
  <backgroundDistortionAmount value="1.000000" />
  <backgroundDistortionBlurLevel value="0" />
  <localLightsMultiplier value="0.200000" />
</rage__ptxgpuDropRenderSettings>
```

**These are the values I would probably play around with & increase to start with** (not *exactly* sure what all of them do)**:**

```xml
  <textureRowsColsStartEnd x="2.000000" y="2.000000" z="0.000000" w="3.000000" />
  <sizeMinMax x="0.025000" y="0.025000" z="0.035000" w="0.035000" />
  <fadeInOut x="1.000000" y="1.000000" />
  <fadeNearFar x="1.000000" y="100.000000" />
  <fadeGrdOffLoHi x="0.000000" y="-15.000000" z="0.500000" w="100.000000" />
  <backgroundDistortionAmount value="1.000000" />
  <backgroundDistortionBlurLevel value="0" />
```

**<sizeMinMax** will have the most dramatic effect. Although it just basically increases the size of the individual snowflakes.