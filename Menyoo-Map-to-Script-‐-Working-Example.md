I posted the template on pastebin, but this is a working example for the [Menyoo Map to Object Placement Map Converter](https://www.gta5-mods.com/tools/menyoo-map-to-object-placement-map-converter) by  @HKH191.

It works very well for certain entities, not as well for others, so you'll need to test yourself. There is a video tutorial but the code was not available in text form so I present it here with a completed template. There are 2 sections for user input. You definitely need basic experience with VS to use this.


```
using GTA;
using GTA.Math;
using GTA.Native;
using System;
using System.Collections.Generic;

namespace MenyooMapConvert
{

    public class Main : Script
    {

        public Main()
        {
            Tick += Ontick;
            Aborted += OnShutDown;
        }


        public ObjectPlacementMap_Example.MissionOjects Map = new ObjectPlacementMap_Example.MissionOjects(new List<ObjectPlacementMap_Example.ObjectPlacementMap>()
        {
        
            // USER INPUT
            // place the output from your xml conversion, same name as Menyoo Map here
            // USE SHVDN 3 PREFERABLY AND ADD ITEM ObjectPlacementMap_Example.cs TO YOUR PROJECT (YOU CAN RENAME IT SHORTER)
          
new ObjectPlacementMap_Example.ObjectPlacementMap(GTA.Native.Function.Call<int>(Hash.GET_HASH_KEY,"Juggalo Female"),348418,0xdb134533, new Vector3(-205.254761f, -804.267883f, 30.4540215f), new Vector3(0f, 0f, 75.0266953f),0x1b06d571,200,0,"false","None","None", -1,-1, new Vector3(0f,0f,0f),new Vector3(0f,0f,0f)),
new ObjectPlacementMap_Example.ObjectPlacementMap(GTA.Native.Function.Call<int>(Hash.GET_HASH_KEY,"Gang Female (Import-Export)"),348674,0x84a1b11a, new Vector3(-204.099762f, -803.107971f, 30.4540272f), new Vector3(0f, -0f, 115.190178f),0x83bf0278,200,0,"false","None","None", -1,-1, new Vector3(0f,0f,0f),new Vector3(0f,0f,0f)),
new ObjectPlacementMap_Example.ObjectPlacementMap(GTA.Native.Function.Call<int>(Hash.GET_HASH_KEY,"Vagos Female"),349186,0x5aa42c21, new Vector3(-205.37059f, -803.325684f, 30.4540215f), new Vector3(0f, -0f, 120.405708f),0x2be6766b,200,0,"false","None","None", -1,-1, new Vector3(0f,0f,0f),new Vector3(0f,0f,0f)),
new ObjectPlacementMap_Example.ObjectPlacementMap(GTA.Native.Function.Call<int>(Hash.GET_HASH_KEY,"Vagos Female"),349442,0x5aa42c21, new Vector3(-204.72377f, -803.728943f, 30.4540215f), new Vector3(0f, -0f, 85.3996811f),0xe284c527,200,0,"false","None","None", -1,-1, new Vector3(0f,0f,0f),new Vector3(0f,0f,0f)),
new ObjectPlacementMap_Example.ObjectPlacementMap(GTA.Native.Function.Call<int>(Hash.GET_HASH_KEY,"Juggalo Female"),349698,0xdb134533, new Vector3(-204.065247f, -804.611145f, 30.4540272f), new Vector3(-0.0263651144f, 0.00956361089f, 81.4525833f),0x394f415c,200,0,"false","None","None", -1,-1, new Vector3(0f,0f,0f),new Vector3(0f,0f,0f)),
new ObjectPlacementMap_Example.ObjectPlacementMap(GTA.Native.Function.Call<int>(Hash.GET_HASH_KEY,"Gang Female (Import-Export)"),349954,0x84a1b11a, new Vector3(-205.151321f, -805.207703f, 30.4540234f), new Vector3(-0.00142294192f, 1.43772056e-07f, 54.9262848f),0x78a97cd0,200,0,"false","None","None", -1,-1, new Vector3(0f,0f,0f),new Vector3(0f,0f,0f)),
new ObjectPlacementMap_Example.ObjectPlacementMap(GTA.Native.Function.Call<int>(Hash.GET_HASH_KEY,"Vagos Female"),350210,0x5aa42c21, new Vector3(-206.628372f, -804.494324f, 30.454031f), new Vector3(0f, 0f, 31.367424f),0x22d8fe39,200,0,"false","None","None", -1,-1, new Vector3(0f,0f,0f),new Vector3(0f,0f,0f)),


        });

        public bool Map_Created;

        public void Ontick(object sender, EventArgs e)
        {
            

            if (!Map_Created)
            {
                              
                for (int i = 0; i < Map.Entities.Count; i++)
                {
                    if (Game.Player.Character.Position.DistanceTo(Map.Entities[i].Position) < 100)
                    {
                        Map_Created = true;
                        Map.CreateEntites();
                    }

                }
                if (Game.Player.Character.Position.DistanceTo(Map.Entities[0].Position) < 100)
                {
                    Map_Created = true;
                    Map.CreateEntites();
                }
                       //SECOND USER INPUT, COORDINATES
                if (Game.Player.Character.Position.DistanceTo(new Vector3(-208.16835f, -803.512756f, 30.4540215f)) < 100) //Your x,y,z coords
                {
                    Map_Created = true;
                    Map.CreateEntites();
                }


            }

        }
        public void OnShutDown(object sender, EventArgs e)
        {
            Map.DeleteEntites();
        }

    } 
}
```