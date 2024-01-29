this has always worked for me
```xml
<Item>
  <filename>dlc_spRagsRiches:/%PLATFORM%/levels/gta5/_citye/downtown_01/dt1_additions.rpf</filename>
  <fileType>RPF_FILE</fileType>
  <overlay value="false" />
  <disabled value="true" />
  <persistent value="true" />
  <contents>CONTENTS_DLC_MAP_DATA</contents>
</Item>
```
you can use it for metadata or just throwing everything in one rpf (imap, ityp, idr, ibn, itd, etc)

For interiors metadata (imap only) I use 
```xml
    <Item>
      <filename>dlc_spRagsRiches:/%PLATFORM%/levels/gta5/interiors/int_placement_sprr.rpf</filename>
      <fileType>RPF_FILE</fileType>
      <overlay value="false" />
      <disabled value="true" />
      <persistent value="true" />
      <loadCompletely value="true" />
      <contents>CONTENTS_DLC_MAP_DATA</contents>
    </Item>
```
and for Interior ityp, idr, ibn, itd, etc I use 
```xml
    <Item>
      <filename>dlc_spRagsRiches:/%PLATFORM%/levels/gta5/interiors/sprr_int_facade_loading_dock.rpf</filename>
      <fileType>RPF_FILE</fileType>
      <overlay value="false" />
      <disabled value="true" />
      <persistent value="true" />
      <contents>CONTENTS_MAP</contents>
    </Item>
```