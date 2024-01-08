@Michualgood 
OpenIV > **Ctrl+F3** > 'Search 'in "mods" folder only' > Search for '**procedural.meta**'

**You should find 2 locations:**

...\Grand Theft Auto V\mods\common.rpf\data\materials\procedural.meta

...\Grand Theft Auto V\mods\update\update.rpf\common\data\materials\procedural.meta

The one in '**update.rpf**' is the one loaded by the game. If it doesn't exist, then the '**common.rpf**' one will be loaded by the game instead.

**Instructions:**
 - Once found, drag & drop '**procedural.meta**' to your Desktop etc
 - Open it with your text editor of choice ([Notepad++](https://notepad-plus-plus.org/downloads/) is better than plain old Notepad)
 - Find & delete the sections ('**<Item>**' to '**</Item>**') of the stuff you want to remove & not have appear ingame:

**Example:** (removing '**prop_barrel_02a**' from seabed)

**Before:**
```xml
    <Item>
      <Tag>SEABED_TRASH_INDUSTRIAL_01</Tag>
      <PlantTag />
      <ModelName>prop_rub_boxpile_08</ModelName>
      <Spacing value="50.000000" />
      <MinXRotation value="0.000000" />
      <MaxXRotation value="0.000000" />
      <MinYRotation value="0.000000" />
      <MaxYRotation value="0.000000" />
      <MinZRotation value="0.000000" />
      <MaxZRotation value="6.281250" />
      <MinScale value="1.000000" />
      <MaxScale value="1.000000" />
      <MinScaleZ value="-1.000000" />
      <MaxScaleZ value="1.000000" />
      <MinZOffset value="0.000000" />
      <MaxZOffset value="0.000000" />
      <MinDistance value="15.000000" />
      <MaxDistance value="60.000000" />
      <MinTintPalette value="1" />
      <MaxTintPalette value="128" />
      <Flags>PROCOBJ_ALIGN_OBJ PROCOBJ_IS_FLOATING</Flags>
    </Item>
    <Item>
      <Tag>SEABED_TRASH_INDUSTRIAL_01</Tag>
      <PlantTag />
      <ModelName>prop_barrel_02a</ModelName>
      <Spacing value="50.000000" />
      <MinXRotation value="6.281250" />
      <MaxXRotation value="6.281250" />
      <MinYRotation value="0.000000" />
      <MaxYRotation value="0.000000" />
      <MinZRotation value="0.000000" />
      <MaxZRotation value="6.281250" />
      <MinScale value="1.000000" />
      <MaxScale value="1.000000" />
      <MinScaleZ value="-1.000000" />
      <MaxScaleZ value="1.000000" />
      <MinZOffset value="0.000000" />
      <MaxZOffset value="0.000000" />
      <MinDistance value="15.000000" />
      <MaxDistance value="60.000000" />
      <MinTintPalette value="1" />
      <MaxTintPalette value="128" />
      <Flags>PROCOBJ_ALIGN_OBJ PROCOBJ_IS_FLOATING</Flags>
    </Item>
    <Item>
      <Tag>SEABED_TRASH_RUBBISH_01</Tag>
      <PlantTag />
      <ModelName>prop_rub_flotsam_02</ModelName>
      <Spacing value="60.000000" />
      <MinXRotation value="0.000000" />
      <MaxXRotation value="0.000000" />
      <MinYRotation value="0.000000" />
      <MaxYRotation value="0.000000" />
      <MinZRotation value="0.000000" />
      <MaxZRotation value="6.281250" />
      <MinScale value="1.000000" />
      <MaxScale value="2.000000" />
      <MinScaleZ value="-1.000000" />
      <MaxScaleZ value="1.000000" />
      <MinZOffset value="-10.000000" />
      <MaxZOffset value="-10.000000" />
      <MinDistance value="50.000000" />
      <MaxDistance value="100.000000" />
      <MinTintPalette value="1" />
      <MaxTintPalette value="128" />
      <Flags>PROCOBJ_ALIGN_OBJ PROCOBJ_IS_FLOATING</Flags>
    </Item>
```
**After:** ('**prop_barrel_02a**' section removed)
```xml
    <Item>
      <Tag>SEABED_TRASH_INDUSTRIAL_01</Tag>
      <PlantTag />
      <ModelName>prop_rub_boxpile_08</ModelName>
      <Spacing value="50.000000" />
      <MinXRotation value="0.000000" />
      <MaxXRotation value="0.000000" />
      <MinYRotation value="0.000000" />
      <MaxYRotation value="0.000000" />
      <MinZRotation value="0.000000" />
      <MaxZRotation value="6.281250" />
      <MinScale value="1.000000" />
      <MaxScale value="1.000000" />
      <MinScaleZ value="-1.000000" />
      <MaxScaleZ value="1.000000" />
      <MinZOffset value="0.000000" />
      <MaxZOffset value="0.000000" />
      <MinDistance value="15.000000" />
      <MaxDistance value="60.000000" />
      <MinTintPalette value="1" />
      <MaxTintPalette value="128" />
      <Flags>PROCOBJ_ALIGN_OBJ PROCOBJ_IS_FLOATING</Flags>
    </Item>
    <Item>
      <Tag>SEABED_TRASH_RUBBISH_01</Tag>
      <PlantTag />
      <ModelName>prop_rub_flotsam_02</ModelName>
      <Spacing value="60.000000" />
      <MinXRotation value="0.000000" />
      <MaxXRotation value="0.000000" />
      <MinYRotation value="0.000000" />
      <MaxYRotation value="0.000000" />
      <MinZRotation value="0.000000" />
      <MaxZRotation value="6.281250" />
      <MinScale value="1.000000" />
      <MaxScale value="2.000000" />
      <MinScaleZ value="-1.000000" />
      <MaxScaleZ value="1.000000" />
      <MinZOffset value="-10.000000" />
      <MaxZOffset value="-10.000000" />
      <MinDistance value="50.000000" />
      <MaxDistance value="100.000000" />
      <MinTintPalette value="1" />
      <MaxTintPalette value="128" />
      <Flags>PROCOBJ_ALIGN_OBJ PROCOBJ_IS_FLOATING</Flags>
    </Item>
```
If you are not sure what something is, use the name in the '**<ModelName>**' line ('**prop_rub_boxpile_08**' etc) & search for that using the **Ctrl+F3** Search Box in OpenIV & you will find it's model/'**.ydr**' & be able to open it & have a look at what it is.

If you want to remove *absolutely everything* from '**procedural.meta**' (decent framerate increase possible (+10>15fps)), make the file look like this & then save & install it:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<CProceduralInfo>
  <procObjInfos>
  </procObjInfos>
  <plantInfos>
  </plantInfos>
  <procTagTable>
  </procTagTable>
</CProceduralInfo>
```

Alternatively, there is a [Reduced Pavement Pollution](https://www.gta5-mods.com/misc/reduced-pavement-pollution) mod that might suit your need.