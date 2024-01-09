I've always got the impression the Eclipse Tower was, at one point, meant to represent the pinnacle of downtown architecture. Personally, I've always deemed the Eclipse Tower rather unimaginative. So, I set out to take one of the fancy Eclipse Penthouse interiors, and move it to **3 Alta Street** -- a much fancier building, IMHO, in the 'banking' district. I adapted my own (private) version of SPA for that. Today I succeeded:

https://youtu.be/tnwJd-qi0Kc

Since I ran into some snares along the way, I decided to make a small beginner's guide about MILO loading, so it will be easier for future peeps playing with MILO files.

For starters, what is MILO? I don't even know for sure, as this game's innards appear to be notoriously undocumented (at least officially); but it's reasonable to assume it stands for **M**oveable **I**nterior **LO**ader. The idea behind a MILO is rather brilliant, really. Instead of hard-coding all your build's objects coordinates, you create a ymap file with just relative coordinates (relative to a, preferably nearby, virtual 'root' prim). That ymap is typically embedded in a **CMloArchetypeDef** container, inside a ytyp file. Like apa_int_mp_h_08.ytyp, used in my project. It creates a CMloArchetypeDef called **apa_V_mp_h_08**, in this case. You can use this interior name in your own MILO loader. Like in the **3alta_aqua_interior_milo_.ymap** I created (which is essentially just an adapted copy of apa_v_mp_h_08_c.ymap):


```
<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<CMapData>
  <name>3alta_aqua_interior_milo_</name>
  <parent/>
  <flags value="1"/>
  <contentFlags value="73"/>
  <streamingExtentsMin x="-12739.02000000" y="-10075.14000000" z="-989.30100000"/>
  <streamingExtentsMax x="7260.98200000" y="9924.85600000" z="5010.69900000"/>
  <entitiesExtentsMin x="-12739.02000000" y="-10075.14000000" z="-989.30100000"/>
  <entitiesExtentsMax x="7260.98200000" y="9924.85600000" z="5010.69900000"/>
  <entities>
    <Item type="CMloInstanceDef">
      <archetypeName>apa_v_mp_h_08</archetypeName>
      <flags value="1572864"/>
      <guid value="752431654"/>
      <position x="-266.301" y="-952.1876" z="95.0"/>
      <rotation x="0.00000000" y="0.00000000" z="0.5701291" w="0.8215551"/>
      <scaleXY value="1.00000000"/>
      <scaleZ value="1.00000000"/>
      <parentIndex value="-1"/>
      <lodDist value="60.00000000"/>
      <childLodDist value="0.00000000"/>
      <lodLevel>LODTYPES_DEPTH_ORPHANHD</lodLevel>
      <numChildren value="0"/>
      <priorityLevel>PRI_REQUIRED</priorityLevel>
      <extensions/>
      <ambientOcclusionMultiplier value="255"/>
      <artificialAmbientOcclusion value="255"/>
      <tintValue value="0"/>
      <groupId value="0"/>
      <floorId value="0"/>
      <defaultEntitySets/>
      <numExitPortals value="4"/>
      <MLOInstflags value="0"/>
    </Item>
  </entities>
  <containerLods/>
  <boxOccluders/>
  <occludeModels/>
  <physicsDictionaries>
    <Item>V_mp_h_08</Item>
  </physicsDictionaries>
  <instancedData>
    <ImapLink/>
    <PropInstanceList/>
    <GrassInstanceList/>
  </instancedData>
  <timeCycleModifiers/>
  <carGenerators/>
  <LODLightsSOA>
    <direction/>
    <falloff/>
    <falloffExponent/>
    <timeAndStateFlags/>
    <hash/>
    <coneInnerAngle/>
    <coneOuterAngleOrCapExt/>
    <coronaIntensity/>
  </LODLightsSOA>
  <DistantLODLightsSOA>
    <position/>
    <RGBI/>
    <numStreetLights value="0"/>
    <category value="0"/>
  </DistantLODLightsSOA>
  <block>
    <version value="0"/>
    <flags value="0"/>
    <name/>
    <exportedBy/>
    <owner/>
    <time/>
  </block>
</CMapData>
```

(Don't forget to set the proper physicsDictionaries too, V_mp_h_08 in this case)

One thing you'll notice, is that you really don't need a Parent loader (most game's MILO's are 'children' of often up to 3-4 levels of inheritance): it works well enough stand-alone. (I was a bit lazy on the extends, but the interior will be totally invisible from the outside anyway). Also note:

    <flags value="1"/>

This is not the usual '0', so the ymap isn't loaded automagically on startup, but only on request. Other contentFlags than 73 are possible, but 73 is a sure bet.

As a sidenote, still well worth mentioning, I think, [CodeWalker](https://www.gta5-mods.com/tools/codewalker-gtav-interactive-3d-map) is awesome! You can just grab the 'root prim' of an entire MILO instance with it, and move/rotate it around as a whole, for your convenience! Chapeau for this great mod!

Now, back to business. One **vital step**, is that your own MILO loader needs a proper _manifest.ymf entry, telling the game where it can find the CMloInstanceDef dependency! Like so:

```
  <imapDependencies_2>
    <Item>
      <imapName>3alta_aqua_interior_milo_</imapName>
      <manifestFlags>INTERIOR_DATA</manifestFlags>
      <itypDepArray>
        <Item>apa_int_mp_h_08</Item>
      </itypDepArray>
    </Item>
  </imapDependencies_2>
```

(Thanks to @nkjellman, for having published his [Leftover Interiors from Beta](https://www.gta5-mods.com/maps/leftover-interiors-from-beta-add-on) mod, so I could study it, and get a clue).

Using this bit of code snippet @Alex106 provided, earlier today (for disabling the MILO physics, after removal), you are now ready to use your own MILO:

	int MPMapAltaStApt = Function.Call<int>(Hash.GET_INTERIOR_AT_COORDS, -266.301f, -952.1876f, 95.0f);
	Function.Call(Hash.SET_INTERIOR_ACTIVE, MPMapAltaStApt, true);
	Function.Call(Hash.DISABLE_INTERIOR, MPMapAltaStApt, false);

(You can use 'ToggleIPL' for this in SPA, btw: plenty examples therein).

That will be it for today! In a next installment, I will address how to make your own moveable CMloArchetypeDef map entries (we still need a good tool to re-calculate fixed coordinated to relative ones, IMHO).

And thanks to the above ppl, and to the always helpful @Cyron43, of course, for kindly giving me access to his bunker loader code. :)