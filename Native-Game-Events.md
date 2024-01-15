I am sharing this little code that let you detect game events such as entity getting damage or killed. There is more events available, need the decompiled scripts to find them.

Also don't hesitate to let me know if I made a mistake or if you have a better way of doing this or if you know more events.

**GET_NUMBER_OF_EVENTS**
https://runtime.fivem.net/doc/natives/?_0x5F92A689A06620AA

**GET_EVENT_AT_INDEX**
https://runtime.fivem.net/doc/natives/?_0xD8F66A3A60C62153

**GET_EVENT_DATA**
https://runtime.fivem.net/doc/natives/?_0x2902843FCD2B2D79

**Events:**
id: 16 = *Seems to be happening when crime is reported (need more test)*
id: 141 = *Damaged*
id: 142 = *Died*

The C# code using Scripthookvdotnet3:
```
private void OnTick(object sender, EventArgs args)
{
    if (Game.Player.IsAlive)
    {
        // Loop all game event this tick and every tick
        for (int x = 0; x < Function.Call<int>(Hash.GET_NUMBER_OF_EVENTS, 0); x++)
        {
            // Get event id
            int eventId = Function.Call<int>(Hash.GET_EVENT_AT_INDEX, 0, x);
            
            string eventName = (eventId == 141) ? "Damaged" : ((eventId == 142) ? "Killed" : "Unknown");
            
            // Prepare objects
            OutputArgument outEntity = new OutputArgument();
            Entity myEntity = null;

            // Get the event data
            if (Function.Call<bool>(Hash.GET_EVENT_DATA, 0, x, outEntity, 1))
            {
                int handle = outEntity.GetResult<int>();
                myEntity = Entity.FromHandle(handle);
                
                // Ignore if event is for player (optional)
                if (handle == Game.Player.Character.Handle) return;

                // Make sure the entity actually exist
                if (myEntity != null && myEntity.Exists())
                {
                    switch(myEntity.EntityType) {
                        case EntityType.Invalid:
                        
                            break;
                        case EntityType.Ped:
                        
                            break;
                        case EntityType.Prop:
                        
                            break;
                        case EntityType.Vehicle:
                        
                            break;
                    }
                }
            }
        }
    }
}
```