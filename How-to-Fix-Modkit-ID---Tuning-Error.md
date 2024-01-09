# [Tutorial] How to Fix Modkit ID / Tuning Error
> ## No problems on my GTA5 - v1.39 / 1.0.1032.1
> ## No problems on my GTA5 - v1.40 / 1.0.1103.2

~~____________________________________________________________________________________________~~
modkit-id numbers make trouble each other sometime.
it's a way of fix tuning error about Modkit-id-numbers.

. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 

**[▼picture]  just 4 Tuning Menu in LSC, the Error from Modkit id number.**
![alt text](http://i.imgur.com/W2O9pd5.jpg)
.

~~____________________________________________________________________________________________~~
# [ Method 1 : Use Default Modkit ]
if u don't need Tuning, recommend to use 'default_modkit' , simple and bug-free.

● Car type : **0_default_modkit**
● Bike type : **0_bike_modkit**
. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 
**[Example]**
**(1) carcols.meta**
Remove the section for the vehicle you want. **(carefully)**

**(2) carvariations.meta**
      <kits>
        <Item>**0_default_modkit**</Item>
      </kits>

.
~~____________________________________________________________________________________________~~
# [ Method 2 : Change Number ]
★★★★★★★★★★★★★★★★★★★★★★★★★★★★★★★
This numbers, not correct answer to every case.
**Recommend use for in your Case only.**
and
it is **Impermanent**. **Possible to Stop Tuning Again,**
when you Update GTA5, or when you install New DLC with Tuning.
★★★★★★★★★★★★★★★★★★★★★★★★★★★★★★★
.

find a mod first,
which mod make trouble with tuning.
and than,
try to change numbers with meta files.
You have to change the number of 2 files Together,
**carcols.meta** and **carvariations.meta**
. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
**[Example]**

**(1) carcols.meta**
      <kitName>**990**_FeF12A_modkit</kitName>
      <id value="**990**" />	

**(2) carvariations.meta**
      <kits>
        <Item>**990**_FeF12A_modkit</Item>
      </kits>


**______________________________________________________**
**[1] No Problem Numbers (v1.39 / 1.0.1032.1 now)**
i'm using this ID in my all-in-1 DLC.
i don't know every mods, who use which numbers.
check your mods first, which Numbers used already.
and choice a number u want.

689
888
889
892
913
914
918
922
937
938
952
961
963
964
965
982
983
984
985
986
987
988
989
990
998
999
1001
1002
1003
1007
1008
1009
1010
1021
1022
1023
1252
1253
1260
1262
1403
1405
1406
1476
1500
1744
2003


**______________________________________________________**
**[2] Other Numbers**
i'm not using this id yet, so i'm not sure.
(this numbers from famous modder's DLC or others community)

175
941
962
979
991~997
1000
1003~1006
1011~1013
1163
1250
1256~1258
766666666
777777777
911111111







**_______________________________________________**
**※ All Numbers [1] +[ 2]**

175
689
888~889
892
913~914
918
922
937~938
941
952
961~965
979
982~999
1000~1013
1021~1023
1163
1250
1252~1253
1256~1258
1260
1262
1403
1405~1406
1476
1500
1744
2003
766666666
777777777
911111111