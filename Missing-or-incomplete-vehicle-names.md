# Vehicle names

Often, add-on vehicles have missing or faulty vehicle names. Here's a quick overview of what files do what, and what you need to change to get things looking nice again.

This guide assumes you've opened the `dlc.rpf` of the vehicle that you want to fix, using OpenIV. The paths are relative to the rpf file when you open it.

In `data/vehicles.meta`, look for these two lines:

```xml
      <gameName>{car model}</gameName>
      <vehicleMakeName>{car brand}</vehicleMakeName>
```

These are just names the game uses internally to look things up. These do not need to look fancy. Make sure both are less than 10 characters and don't contain spaces, keep it simple. An example for an Alfa Romeo Giulia Quadrifoglio:

```xml
      <gameName>giuliaq</gameName>
      <vehicleMakeName>alfaromeo</vehicleMakeName>
```

In `x64/data/lang/{language}.rpf` there is one `global.gxt2`. If not, we're going to create one. If it's there, right-click it and select `Export to openFormat Text File (.oxt)`.

Open the `global.oxt`. It should look something like this:

```
Version 2 30
{
	// here be content
}
```

Some add-on car makers dump a lot of stuff in here. You can either add to it, or just add the one name that the `dlc.rpf` file actually contains.

Fill it in like so:

```
Version 2 30
{
	alfaromeo = Alfa Romeo
	giuliaq = Giulia Quadrifoglio
}
```

Save the file, and drag it back into the `{language}.rpf` file. OpenIV should put it back as `global.gxt2`.

If you play in English, `americandlc.rpf` is the file you want to edit. For other languages, change the appropriate `{language}.rpf`.

Now open the game - when entering the car or spawning the car, it should be represented with the correct full name.

---------------------

## No existing language files

Sometimes, a `dlc.rpf` may not come with language files at all. These can be added, but require a bit more work.

For reference, open a `dlc.rpf` that you know works, and compare/copy over the `dlctext.meta`-related entries:

* In `content.xml` specify that `dlctext.meta` exists within `dataFiles` and `filesToEnable`
* Then copy a `dlctext.meta` to the folder (in `data/` probably). Make sure `<hasGlobalTextFile value="true"/>` is in there.
* Create the folder structure (at `x64/data/lang/`) with the `{language}.rpf` files.

It *should* work then, but I haven't attempted this myself yet, some more actions may be needed.

---------------------

## Hashes

Note that when opening an existing language file, OpenIV may not know what's left of the `=` sign and show it as a "hash", like `0x61FF5B8B`. This hash is what the game uses to look things up. In this case, "hashing" the string "alfaromeo" results in `0x61FF5B8B`. The line `alfaromeo = Alfa Romeo` is exactly the same as `0x61FF5B8B = Alfa Romeo`.

Left of `=` means the internal name or hash.

Right of `=` is the actual name how it's displayed in the game.

