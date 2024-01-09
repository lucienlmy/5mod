I've recently been swapping M, T and F with non-streamed/normal models (i.e. models that consists of only 4 files) and I though I could share with you guys how I did that using only OpenIV.

For this example, I swapped Franklin with Arena War's Bryony. First, I exported csb_bryony.ydd and csb_bryony.ytd as open formats, exporting them as .odd and .otd files respectively. To transfer her glasses, I also exported csb_bryony_p.ydd and csb_bryony_p.ytd to open formats. I then exported csb_bryony.ymt and csb_bryony.yft as normal and renamed them player_one.ymt and player_one.yft respectively. 

You will now need to create new .odd and .otd files inside the csb_bryony folder OpenIV created when you exported the .ydd and .ytd files. ODD and OTD files reference .odr and .otx files respectively and OpenIV will automatically convert them YDD or YTD files respectively when you drag them into a RPF. The structure of ODD and OTD files are rather simple and can be edited with a text editor. For a streamed model, an OTD file will look like this:

Version 13 30
{
	uppr_diff_000_a_uni.otx
}

An ODD file:

Version 165 32
{
	accs_000_u.odr
}

Inside csb_bryony, I created the following ODD files (they all reference ODR files of the same name)
* accs_000_u.odd
* feet_000_u.odd
* hair_000_u.odd
* head_000_r.odd
* jbib_000_u.odd
* lowr_000_r.odd
* task_000_u.odd
* uppr_000_r.odd

Rename ODR files if necessary so that they will match with the ODD files. I also found adding ".otx" to the ends DiffuseSampler, BumpSampler and SpecSampler files also helps fixes texture issues.

In the same folder, I created the following OTD files (most reference OTX files of the same name):
* accs_diff_000_a_uni.otd
* feet_diff_000_a_uni.otd
* hair_diff_000_a_uni.otd
* head_diff_000_a_bla.otd -> this file will reference head_diff_000_a_whi.otx
* jbib_diff_000_a_uni.otd
* lowr_diff_000_a_whi.otd
* task_diff_000_a_uni.otd
* uppr_diff_000_a_whi.otd

These OTD file names should match the file of the DiffuseSampler being referenced in the ODR file.

Inside csb_bryony_p, create the following files:
* p_eyes_000.odd
* p_eyes_diff_000_a.otd

Drag the ODD and OTD files from csb_bryony to mods\x64v.rpf\models\cdimages\streamedpeds_players.rpf\player_one and from csb_bryony_p to mods\x64v.rpf\models\cdimages\streamedpedprops.rpf\player_one_p (I also recommend deleting all the existing ydd and ytd files inside player_one). Replace player_one.ymt and player_one.yft with your modded ymt and yft files. Don't forget to delete the player_one files and folders in mppatchesng and patchday3ng. After starting up the game, use a trainer to give Bryony her glasses.

I also decided to replace Michael and Trevor with Sacha Yetarian (ig_sacha) and Alan Jerome (csb_alan) respectively. I won't go into detail on how I did that, but I will show you the .ydd and ytd files that I ended up using for both:
![alt text](https://i.imgur.com/O0KZlwr.jpg)
![alt text](https://i.imgur.com/ycddkwW.jpg)

For Trevor, you will also need to replace decl_000_u.ydd with a "blank" ydd file inside mods\update\x64\dlcpacks\mpheist\dlc.rpf\x64\models\cdimages\trevor_outfits.rpf\player_two_trevor_heist, or else you'll have a TP Industries decal floating on top of your character. You can simple use decl_000_u.ydd inside x64v.rpf\models\cdimages\streamedpeds_mp.rpf\mp_m_freemode_01 as a replacement/

Here are some screenshots of the three protagonists replaced by the Arena War characters:

![alt text](https://i.imgur.com/taqSXwy.jpg)
![alt text](https://i.imgur.com/KUKJ0Jb.jpg)
![alt text](https://i.imgur.com/JKvlogF.jpg)
![alt text](https://i.imgur.com/ZtKlU2F.jpg)
![Sacha Yetarian, Bryony and Alan Jerome](https://i.imgur.com/NEkSOrS.jpg)

And here's a video I made of this model swap (because ig_sacha has no lip movements, I replaced him with someone else):
[![Audi R8](http://img.youtube.com/vi/JLhleGWAUjE/0.jpg)](https://www.youtube.com/watch?v=JLhleGWAUjE "Bryony kills Alan")

You can also download the mod here:
https://drive.google.com/open?id=1SLTeOAWLZvUHIPjAZswJiI9GRWV3KvBe

Finally, you might be wondering why I decided to go through all of this instead of using [Unknown Modder's Character Swap](https://www.gta5-mods.com/scripts/character-swap) mod. The reason is that Unknown Modder's Character Swap mod only swaps one character at a time, while this method allows to swap multiple characters at once. Also, that Character Swap doesn't seem to carry through when you replay certain missions, including Something Sensible.