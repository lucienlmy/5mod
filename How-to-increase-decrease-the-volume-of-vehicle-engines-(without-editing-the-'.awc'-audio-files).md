@InfiniteQuestion said in [\[ Tutorial \] \- How to increase/decrease the volume of vehicle engines \(without editing the &apos;\.awc&apos;\)](/post/166273):
> The car was using the Electric Engine line, and not the granular line

Nice catch :thumbsup:

@InfiniteQuestion said in [\[ Tutorial \] \- How to increase/decrease the volume of vehicle engines \(without editing the &apos;\.awc&apos;\)](/post/166273):
>  i'm gonna try to swap the engine sounds in the rel.

By my understanding, there should be a few different ways to do that. :thumbsup:

Either, by using the:
```xml
   <Wave1>
    <ContainerName>streamed_vehicles_granular/muscle_car_2_us_v8</ContainerName>
    <FileName>engine_accel</FileName>
   </Wave1>
   <Wave2>
    <ContainerName>streamed_vehicles_granular/muscle_car_2_us_v8</ContainerName>
    <FileName>exhaust_accel</FileName>
   </Wave2>
   <Wave3>
    <ContainerName>streamed_vehicles_granular/muscle_car_2_us_v8</ContainerName>
    <FileName>engine_decel</FileName>
   </Wave3>
   <Wave4>
    <ContainerName>streamed_vehicles_granular/muscle_car_2_us_v8</ContainerName>
    <FileName>exhaust_decel</FileName>
   </Wave4>
   <Wave5>
    <ContainerName>streamed_vehicles_granular/muscle_car_2_us_v8</ContainerName>
    <FileName>engine_idle</FileName>
   </Wave5>
   <Wave6>
    <ContainerName>streamed_vehicles_granular/muscle_car_2_us_v8</ContainerName>
    <FileName>exhaust_idle</FileName>
   </Wave6>
```
'**ContainerName**' directory lines in '**sounds.dat54.rel.xml**' to point to a different '**.awc**'.

**OR**
 
by changing the:
```xml
   <EngineAccel>hash_9B652D9B</EngineAccel>
   <ExhaustAccel>hash_B4D51AE7</ExhaustAccel>
```
hash values in '**game.dat151.rel.xml**' to point to a different '**<Item type="GranularSound">**' section in '**sounds.dat54.rel.xml**'.

**Note:**
Using the '**Engine/ExhaustAccel'** hashes there in '**game.dat151.rel.xml**', it's possible to mix & match different vehicle's engine & exhaust sounds together on the one vehicle. 
That's *not* possible mixing & matching the '**ContainerName**' lines in '**sounds.dat54.rel.xml**' as it causes the vehicle to have a silent engine in-game. 

I'm basically just throwing out the things I've discovered, more for the next person who comes along to read it, it may or may not be relevant to what you are doing :smile:, I'm sure you've got it covered :thumbsup:

**Extra General Info**:
I've been playing around with the '**<Unk##**' values & swapping the odd '**hash_########**' value here & there.
They do make changes to how the engine sounds, but it's all pretty subtle (bar the odd time I got a muscle car with a gokart engine lol).

R*'s naming conventions seem to be a little off in places too. Not always the most logical choice of names for connected files etc.
 
In some vehicles at least, the:
```xml
   <EngineLow>hash_F045343B</EngineLow>
   <EngineHigh>hash_682D2137</EngineHigh>
   <ExhaustLow>hash_E3C6AD67</ExhaustLow>
   <ExhaustHigh>hash_93833621</ExhaustHigh>
```
hashes seem to use a different *numbered* '**.awc**' than the one used for the granular '**EngineAccel/ExhaustAccel**'.

**Example:**
The Vigero seems to use '**muscle_car_3.awc**' (in '**STREAMED_VEHICLES.rpf**') for it's '**EngineLow/High**' & it's '**ExhaustLow/High**' audio, while it obviously uses the '**muscle_car_2_us_v8.awc**' (in '**STREAMED_VEHICLES_GRANULAR.rpf**') for it's granular engine & exhaust sound ('**muscle_car_2_**' for both would have been a more logical choice etc).

Just something to be aware of. It's only numbering I guess, but I could see it catching someone out. Don't make no presumptions where R* is concerned etc. :thumbsup: