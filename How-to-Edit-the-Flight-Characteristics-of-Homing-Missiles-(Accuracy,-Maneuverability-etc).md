In this tutorial you'll learn how to make homing missiles more accurate/maneuverable & thus, stay locked to the enemy vehicle *even* if they miss/fly past on the first attempt.

Below I give an example using the [Homing Launcher](https://gta.fandom.com/wiki/Homing_Launcher) missile, but all the info applies to all homing missiles, including aircraft ones etc. If editing a different missile, either copy the pertinent data from the example (minus the '**<Name>**' & '**<Model>**' lines ofc), or if you prefer editing you own file, refer to the '**Important values:**' section below & edit your missile's '**AMMO/'CAmmoRocketInfo'**' section accordingly.

**Note:**
You can find the **AMMO/'CAmmoRocketInfo'** section your weapon is using in the '**<AmmoInfo ref=**' line of that weapon in it's '**weapon/*weapon-name-here*.meta**'.

**Making Homing Launcher (or *any*) Missile More Accurate & Reacquire Lock if it Flies Past Enemy (Air) Vehicle:**
-
**Note:**
It's probably possible to get the '*fly around vehicle/reacquire lock after initial miss*' parts to work effectively for ground vehicles also. Obviously, as it stands, the missile (if it misses first time etc) will likely hit the ground or an object as it tries to fly over & around a ground based vehicle, but it may be possible to reduce the missile's ability to use Pitch & Roll, & thus, force it to fly around targets more on a horizontal axis/plane (rather than over & under/on a vertical/diagonal axis/plane etc)

**Example:** (Homing Launcher)

Find the '**weaponhominglauncher.meta**' here:

...\Grand Theft Auto V\mods\update\update.rpf\dlc_patch\mpchristmas2\common\data\ai\weaponhominglauncher.meta

**Note:** Make sure to edit the '**weaponhominglauncher.meta**' in '**update.rpf\dlc_patch\\mpchristmas2**', *not* the one in '**dlcpacks\mpchristmas2**' :thumbsup:

Open that '**weaponhominglauncher.meta**' & edit the '**AMMO_HOMINGLAUNCHER**' section to look like this (make a backup first if previously edited etc):
```xml
        <Item type="CAmmoRocketInfo">
          <Name>AMMO_HOMINGLAUNCHER</Name>
          <Model>w_lr_homing_rocket</Model>
          <Audio />
          <Slot />
          <AmmoMax value="10" />
          <AmmoMax50 value="10" />
          <AmmoMax100 value="10" />
          <AmmoMaxMP value="10" />
          <AmmoMax50MP value="10" />
          <AmmoMax100MP value="10" />
          <AmmoFlags>AddSmokeOnExplosion</AmmoFlags>
          <Damage value="0.000000" />
          <LifeTime value="100.000000" />
          <FromVehicleLifeTime value="100.000000" />
          <LifeTimeAfterImpact value="0.000000" />
          <LifeTimeAfterExplosion value="0.000000" />
          <ExplosionTime value="0.000000" />
          <LaunchSpeed value="1200.000000" />
          <SeparationTime value="0.000000" />
          <TimeToReachTarget value="15.000000" />
          <Damping value="0.000000" />
          <GravityFactor value="0.020000" />
          <RicochetTolerance value="0.000000" />
          <PedRicochetTolerance value="0.000000" />
          <VehicleRicochetTolerance value="0.000000" />
          <FrictionMultiplier value="1.000000" />
          <Explosion>
            <Default>ROCKET</Default>
            <HitCar>CAR</HitCar>
            <HitTruck>TRUCK</HitTruck>
            <HitBike>BIKE</HitBike>
            <HitBoat>BOAT</HitBoat>
            <HitPlane>PLANE</HitPlane>
          </Explosion>
          <FuseFx />
          <TrailFx>proj_rpg_trail</TrailFx>
          <TrailFxUnderWater />
          <FuseFxFP />
          <PrimedFxFP />
          <TrailFxFadeInTime value="0.000000" />
          <TrailFxFadeOutTime value="0.000000" />
          <PrimedFx />
          <DisturbFxDefault>proj_disturb_dust</DisturbFxDefault>
          <DisturbFxSand>proj_disturb_dust</DisturbFxSand>
          <DisturbFxWater>proj_disturb_dust</DisturbFxWater>
          <DisturbFxDirt>proj_disturb_dust</DisturbFxDirt>
          <DisturbFxFoliage>proj_disturb_dust</DisturbFxFoliage>
          <DisturbFxProbeDist value="0.000000" />
          <DisturbFxScale value="0.000000" />
          <LightOnlyActiveWhenStuck value="false" />
          <LightFlickers value="false" />
          <LightSpeedsUp value="false" />
          <LightBone />
          <LightColour x="0.000000" y="0.000000" z="0.000000" />
          <LightIntensity value="0.000000" />
          <LightRange value="0.000000" />
          <LightFalloffExp value="0.000000" />
          <LightFrequency value="0.000000" />
          <LightPower value="0.000000" />
          <CoronaSize value="0.000000" />
          <CoronaIntensity value="0.000000" />
          <CoronaZBias value="0.000000" />
          <ProjectileFlags>DestroyOnImpact ProcessImpacts DoGroundDisturbanceFx</ProjectileFlags>
          <UntriggeredProximityLightColour x="0.000000" y="0.000000" z="0.000000" />
          <ForwardDragCoeff value="0.900000" />
          <SideDragCoeff value="0.000000" />
          <TimeBeforeHoming value="2.000000" />
          <TimeBeforeSwitchTargetMin value="1.250000" />
          <TimeBeforeSwitchTargetMax value="2.500000" />
          <ProximityRadius value="0.000000" />
          <PitchChangeRate value="9999.000000" />
          <YawChangeRate value="9999.000000" />
          <RollChangeRate value="9999.000000" />
          <MaxRollAngleSin value="0.000000" />
          <LifeTimePlayerVehicleLockedOverrideMP value="-1.000000" />
        </Item>
```

That should improve the accuracy & also make the rockets turn around & come after the enemy vehicle if they miss with the first try (as long as they don't hit something else/glitch out of existence (which *can* happen *occasionally*)). To get the most out it, certain values need to be balanced depending on what '**<LaunchSpeed value**' you are using. That's why I posted the full '**AMMO_HOMINGLAUNCHER**' section for you to test out & confirm it work etc. :thumbsup:
It's good that way tho, it offers a lot of flexibility, allowing you to create pretty much whatever missile behaviour you want. It's even possible to delicately edit the values to force the missile to fly around an air vehicle in a circle arc indefinitely, or do that several times in certain situations before hitting the air vehicle if/when the pilot changes trajectory & the missile can reach the target etc.

**Important values:**

 - '**<LaunchSpeed value':**
Speed of missle, the higher this is the less the missle can turn (all other values being equal). Higher values can be compensated for by lowering the '**<SideDragCoeff value**' & raising the '**<ForwardDragCoeff value'**.

 - '**<ForwardDragCoeff value=':**
Drag on the front of the missile. Higher '**<ForwardDragCoef**' values *combined* with lower '**<SideDragCoeff**' values allow the missle to turn in a tighter circle/arc.
 - '**<SideDragCoeff value':**
Drag on the side/back of the missile when it is turning. Lower values *combined* with higher '**<ForwardDragCoef**' values allow the missile to turn in a tighter circle/arc. Just set it to zero/'**0.000000**' for max maneuverability etc
 - '**Pitch/Yaw/RollChangeRate' values:**
How quickly/how much the missile reacts with Pitch/Yaw/Roll within the confines of the '**<Forward/SideDragCoef**' values. As the missile is constantly flying forward the lower these values are the less the missile will be able to turn fast & tight. So, set them high ('**9999**' etc) if you want the max maneuverability.
 - **'<MaxRollAngleSin value':**
*Likely* a Sine function value (range -1 to 1 if so). Hard to see what effect changing the value has on the missile's ability to roll. I'd likely have to use a 'missile cam' to see the flight characteristics in any detail. May well be that the roll capability becomes less pronounced/important once the missile can turn in a tighter arc with the other values above etc. Setting it to **0.0000** seems to work well enough anyway, but feel free to experiment with the value once you have the other values dialed in.