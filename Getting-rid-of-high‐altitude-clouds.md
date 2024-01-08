You can definitely remove them by editing '**clouds.xml**'
Usually here: 
...\Grand Theft Auto V\mods\common.rpf\data\clouds.xml

**Note:** Use **Ctrl+F3** in OpenIV to make sure you don't also have one in '**update.rpf**' that will be overriding that one in '**common.rpf**'.

Once you find the correct file loaded by the game, edit it & remove all the blocks of data with '**altitude**' in the '**<mFilename>**' lines.

The ones like this:

```xml
        <Item>
          <mFilename>cloudhat_altitude_med_b</mFilename>
          <mCostFactor value="0.000000" />
          <mRotationScale value="0.500000" />
          <mCamPositionScalerAdjust value="1.000000" />
          <mTransitionInTimePercent value="0.400000" />
          <mTransitionOutTimePercent value="0.400000" />
          <mTransitionInDelayPercent value="0.000000" />
          <mTransitionOutDelayPercent value="0.000000" />
          <mHeightTigger value="800.000000" />
          <mHeightFadeRange value="400.000000" />
        </Item>
```
That should get rid of them horrible clouds. 
