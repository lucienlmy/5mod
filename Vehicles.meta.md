#### My third tutorial. 
Here's *another* META file. 
## The Vehicles.meta.
----

Vehicles.meta defines vehicles and their properties. 
This file is located in xxxx.rpf\common\data\levels\gta5



Examples: 

* Grand Theft Auto V\mods\update\update.rpf\common\data\levels\gta5
* Grand Theft Auto V\mods\update\x64\dlcpacks\mpstunt\dlc.rpf\common\data\levels\gta5

#### Like the Handling.meta, this tutorial will be useful for new modders.

# 1. Parameters

### 1.1 modelName
* Name of the model.

Example: 
<modelName>blista</modelName>

### 1.2 txdName

* Name of the vehicle's texture dictionary.

Example: 
<txdName>blista</txdName>

### 1.3. handlingId

* The name used in handling.meta. Default names are written in uppercase.

### 1.4. gameName

* The vehicle's name corresponding to its **GXT2** entry.
* **Displayed when entering the vehicle.**

### 1.5. vehicleMakeName

* The vehicle maker's/manufacturer's  name corresponding to its **GXT2** entry.
* Default names are written in uppercase.

Examples:
* <vehicleMakeName>DINKA</vehicleMakeName>
* <vehicleMakeName>DECLASSE</vehicleMakeName>

### 1.6. expressionDictName
### 1.7. expressionName
### 1.8. animConvRoofDictName
* Name of Convertible vehicles' roof opening animation.
### 1.9. animConvRoofName
### 1.10. animConvRoofWindowsAffected
* Names of the affected windows when a convertible's roof retracts.
IDs used:
<Item>VEH_EXT_WINDOW_LF</Item>
<Item>VEH_EXT_WINDOW_RF</Item>
<Item>VEH_EXT_WINDOW_LR</Item>
<Item>VEH_EXT_WINDOW_RR</Item>
<Item>VEH_EXT_WINDSCREEN_R</Item>

### 1.11.ptfxAssetName
### 1.12. audioNameHash
* Sound of the vehicle.

### 1.13. layout

Layout decribes how big the vehicle's collisions are , and how does a play enter it. And the sitting positions of the seats. And the number of doors. And how the doors act.
*@FoxtrotDelta Thanks.*

Parameters used:
Many of these are really obvious.
LAYOUT_STD_LOWROOF
LAYOUT_STANDARD
LAYOUT_TRUCK
LAYOUT_BUS
LAYOUT_COACH
LAYOUT_VAN_CADDY
LAYOUT_VAN
LAYOUT_TRUCK_BARRACKS
LAYOUT_STD_HIGHWINDOW - used for Crossovers and small SUVs.
LAYOUT_VAN_MULE
LAYOUT_LOW_BFINJECTION
LAYOUT_TRUCK_BIFF
LAYOUT_BIKE_QUAD
LAYOUT_BISON
LAYOUT_VAN_BOXVILLE
LAYOUT_VAN_BODHI
LAYOUT_BULLDOZER
LAYOUT_LOW_RESTRICTED
LAYOUT_BLIMP
LAYOUT_RANGER
LAYOUT_VAN_POLICE
LAYOUT_TRAIN
LAYOUT_LOW_CHEETAH
LAYOUT_CUTTER
LAYOUT_LOW_DUNE
LAYOUT_VAN_TRASH
LAYOUT_4X4
LAYOUT_DUMPTRUCK
LAYOUT_TRUCK_DOCKTUG
LAYOUT_STD_EXITFIXUP
LAYOUT_LOW_ENTITYXF
LAYOUT_FIRETRUCK
LAYOUT_FORK_LIFT
LAYOUT_STD_HABANERO
LAYOUT_CRANE
LAYOUT_LOW_INFERNUS
LAYOUT_VAN_JOURNEY
LAYOUT_TRUCK_MIXER
LAYOUT_TRUCK_TOW
LAYOUT_MOWER
LAYOUT_PRISON_BUS
LAYOUT_VAN_PONY
LAYOUT_STD_RIPLEY
LAYOUT_TOURBUS
LAYOUT_TANK
LAYOUT_RIOT_VAN
LAYOUT_RANGER_SANDKING
LAYOUT_STD_STRATUM
LAYOUT_ONE_DOOR_VAN
LAYOUT_TRACTOR2
LAYOUT_STD_STRETCH
LAYOUT_STD_ZTYPE
LAYOUT_BIKE_DIRT
LAYOUT_BICYCLE_MOUNTAIN
LAYOUT_BICYCLE_ROAD
LAYOUT_BICYCLE_FIXTER
LAYOUT_BICYCLE_CRUISER
LAYOUT_BICYCLE_BMX
LAYOUT_BIKE_POLICE
LAYOUT_BIKE_SPORT
LAYOUT_BIKE_FREEWAY
LAYOUT_BIKE_SPORT_BATI
LAYOUT_BIKE_CHOPPER
LAYOUT_BIKE_SCOOTER
LAYOUT_HELI_ANNIHILATOR
LAYOUT_HELI_BUZZARD
LAYOUT_HELI
LAYOUT_HELI_CARGOBOB
LAYOUT_HELI_SKYLIFT
LAYOUT_HELI_FROGGER
LAYOUT_PLANE_CUBAN
LAYOUT_PLANE_DUSTER
LAYOUT_PLANE_STUNT
LAYOUT_PLANE_MAMMATUS
LAYOUT_PLANE_JUMBO
LAYOUT_PLANE_JET
LAYOUT_PLANE_TITAN
LAYOUT_PLANE_LAZER
LAYOUT_BOAT_SQUALO
LAYOUT_BOAT_MARQUIS
LAYOUT_BOAT_DINGHY
LAYOUT_BOAT_JETMAX
LAYOUT_BOAT_PREDATOR
LAYOUT_BOAT_TROPIC
LAYOUT_BOAT_JETSKI
LAYOUT_BOAT_SUBMERSIBLE
LAYOUT_UNKNOWN
LAYOUT_PLANE_VELUM
LAYOUT_BOAT_SUNTRAP

### 1.14. coverBoundOffsets
### 1.15. explosionInfo

Used parameters:

EXPLOSION_INFO_DEFAULT
EXPLOSION_INFO_TRUCK
EXPLOSION_INFO_TANKER
EXPLOSION_INFO_PROPTRAILER
EXPLOSION_INFO_JET
EXPLOSION_INFO_TITAN
EXPLOSION_INFO_BOAT_MEDIUM
EXPLOSION_INFO_MARQUIS
EXPLOSION_INFO_BOAT_SMALL

### 1.16. scenarioLayout[edit]
### 1.17. cameraName

Used Parameters:

DEFAULT_FOLLOW_VEHICLE_CAMERA
FOLLOW_ARTIC_CAMERA
FOLLOW_UPRIGHT_BIKE_CAMERA
FOLLOW_JEEP_CAMERA
FOLLOW_MAVERICK_CAMERA
FOLLOW_CHEETAH_CAMERA
FOLLOW_CUTTER_CAMERA
FOLLOW_FORKLIFT_CAMERA
FOLLOW_HANDLER_CAMERA
FOLLOW_TANK_CAMERA
FOLLOW_TACO_CAMERA
FOLLOW_BICYCLE_CAMERA
FOLLOW_UPRIGHT_BICYCLE
FOLLOW_HELI_CAMERA
FOLLOW_SKYLIFT_CAMERA
FOLLOW_MAVERICK_CAMERA
FOLLOW_PLANE2_CAMERA
FOLLOW_PLANE_CAMERA
FOLLOW_TITAN_CAMERA
FOLLOW_LAZER_CAMERA
FOLLOW_BOAT_CAMERA
FOLLOW_YACHT_CAMERA
FOLLOW_DINGHY_CAMERA
FOLLOW_JETSKI_CAMERA
FOLLOW_MINISUB_CAMERA

### 1.18. aimCameraName
### 1.19. bonnetCameraName
### 1.20.bonnetCameraName
### 1.21.First Person IK Offsets
* Inverse kinematics offsets when using first person view.

Parameters: 

#### FirstPersonDriveByIKOffset
#### FirstPersonDriveByUnarmedIKOffset
#### FirstPersonProjectileDriveByIKOffset
#### FirstPersonProjectileDriveByPassengerIKOffset
#### FirstPersonProjectileDriveByRearLeftIKOffset
#### FirstPersonProjectileDriveByRearRightIKOffset
#### FirstPersonDriveByLeftPassengerIKOffset
#### FirstPersonDriveByRightPassengerIKOffset
#### FirstPersonDriveByRightRearPassengerIKOffset
#### FirstPersonDriveByLeftPassengerUnarmedIKOffset
#### FirstPersonDriveByRightPassengerUnarmedIKOffset
#### FirstPersonMobilePhoneOffset
#### FirstPersonPassengerMobilePhoneOffset

### 1.22. PovCameraOffset
* Adjusts the first person camera.
### 1.23. PovCameraVerticalAdjustmentForRollCage
### 1.24. PovPassengerCameraOffset
### 1.25. PovRearPassengerCameraOffset
### 1.26. vfxInfoName
### 1.27. shouldUseCinematicViewMode value
### 1.28. shouldCameraTransitionOnClimbUpDown value
### 1.29. shouldCameraIgnoreExiting value
### 1.30. AllowPretendOccupants value
### 1.31. AllowJoyriding value
### 1.32. AllowSundayDriving value
### 1.33. AllowBodyColorMapping value
### 1.34. wheelScale value
### 1.35. wheelScaleRear value

### 1.36. dirtLevelMin value
### 1.37. dirtLevelMax value
* Controls how much dirty the vehicle be when driving off-road.

### 1.38. envEffScaleMin value 
### 1.39. envEffScaleMax value
### 1.40. envEffScaleMin2 value
### 1.41. envEffScaleMax2 value
### 1.42. damageMapScale value
### 1.43. damageOffsetScale value
### 1.44. diffuseTint  value
### 1.45. steerWheelMult value
### 1.46. HDTextureDist value
### 1.47. lodDistances content="float_array"

* Distances LOD models. 

Default parameters:

15.000000
30.000000
70.000000	
140.000000	
500.000000	
500.000000
      
### 1.48. identicalModelSpawnDistance value
### 1.49. maxNumOfSameColor value
### 1.50. defaultBodyHealth value
### 1.51. pretendOccupantsScale value
### 1.52. visibleSpawnDistScale value
### 1.53. trackerPathWidth value
### 1.54. weaponForceMult value
### 1.55. frequency value
### 1.56. swankness
### 1.57. maxNum value
### 1.58. flags

Available flags:


* FLAG_ALLOW_HATS_NO_ROOF
* FLAG_ALLOWS_RAPPEL
* FLAG_ATTACH_TRAILER_IN_CITY
* FLAG_ATTACH_TRAILER_ON_HIGHWAY
* FLAG_AVERAGE_CAR
* FLAG_AVOID_TURNS
* FLAG_BIG
* ALLOW_OBJECT_LOW_LOD_COLLISION
* FLAG_BIKE_CLAMP_PICKUP_LEAN_RATE
* FLAG_BLOCK_FROM_ATTRACTOR_SCENARIO
* FLAG_BOOT_IN_FRONT
* FLAG_CAN_BE_DRIVEN_ON
* FLAG_CAN_HAVE_NEONS
* FLAG_CAN_HONK_WHEN_FLEEING
* FLAG_CANNOT_BE_DRIVEN_BY_PLAYER
* FLAG_CANNOT_BE_MODDED
* FLAG_CANNOT_BE_PICKUP_BY_CARGOBOB
* FLAG_CANNOT_TAKE_COVER_WHEN_STOOD_ON
* FLAG_CONSIDERED_FOR_VEHICLE_ENTRY_WHEN_STOOD_ON
* FLAG_COUNT_AS_FACEBOOK_DRIVEN
* FLAG_DAMPEN_STICKBOMB_DAMAGE
* FLAG_DELIVERY
* FLAG_DISABLE_AUTO_VAULT_ON_VEHICLE
* FLAG_DISABLE_BUSTING
* FLAG_DISABLE_THROUGH_WINDSCREEN
* FLAG_DISABLE_WEAPON_WHEEL_IN_FIRST_PERSON
* FLAG_DONT_CLOSE_DOOR_UPON_EXIT
* FLAG_DONT_ROTATE_TAIL_ROTOR
* FLAG_DONT_SPAWN_AS_AMBIENT
* FLAG_DONT_SPAWN_IN_CARGEN
* FLAG_DONT_STOP_WHEN_GOING_TO_CLIMB_UP_POINT
* FLAG_DONT_TIMESLICE_WHEELS
* FLAG_DRIVER_NO_DRIVE_BY
* FLAG_DRIVER_SHOULD_BE_MALE
* FLAG_EMERGENCY_SERVICE
* FLAG_EXPLODE_ON_CONTACT
* FLAG_EXTRAS_ALL
* FLAG_EXTRAS_CONVERTIBLE
* FLAG_EXTRAS_GANG
* FLAG_EXTRAS_ONLY_BREAK_WHEN_DESTROYED
* FLAG_EXTRAS_RARE
* FLAG_EXTRAS_REQUIRE
* FLAG_EXTRAS_SCRIPT
* FLAG_EXTRAS_STRONG
* FLAG_EXTRAS_TAXI
* FLAG_FAKE_EXTRALIGHTS
* FLAG_FLEE_FROM_COMBAT
* FLAG_FORCE_ENABLE_CHASSIS_COLLISION
* FLAG_GEN_NAVMESH
* FLAG_GIVE_SCUBA_GEAR_ON_EXIT
* FLAG_HAS_BULLETPROOF_GLASS
* FLAG_HAS_DIRECTIONAL_SHUFFLES
* FLAG_HAS_INTERIOR_EXTRAS
* FLAG_HAS_LIVERY
* FLAG_HAS_NO_ROOF
* FLAG_HAS_REAR_MOUNTED_TURRET
* FLAG_HAS_TURRET_SEAT_ON_VEHICLE
* FLAG_HEADLIGHTS_ON_LANDINGGEAR
* FLAG_HEADLIGHTS_USE_ACTUAL_BONE_POS
* FLAG_HELI_USES_FIXUPS_ON_OPEN_DOOR
* FLAG_IGNORE_ON_SIDE_CHECK
* FLAG_IGNORE_RWINDOW_COLLISION
* FLAG_INCREASE_PED_COMMENTS
* FLAG_INTERIOR_BLOCKED_BY_BOOT
* FLAG_IS_BULKY
* FLAG_IS_BUS
* FLAG_IS_ELECTRIC
* FLAG_IS_JETSKI
* FLAG_IS_OFFROAD_VEHICLE
* FLAG_IS_TANK
* FLAG_IS_VAN
* FLAG_LAW_ENFORCEMENT
* FLAG_NO_BOOT
* FLAG_NO_BROKEN_DOWN_SCENARIO
* FLAG_NO_RESPRAY
* FLAG_PARKING_SENSORS
* FLAG_PEDS_CAN_STAND_ON_TOP
* FLAG_PEDS_INSIDE_CAN_BE_SET_ON_FIRE_MP
* FLAG_PLANE_WEAR_ALTERNATIVE_HELMET
* FLAG_PREFER_ENTER_TURRET_AFTER_DRIVER
* FLAG_RECESSED_HEADLIGHT_CORONAS
* FLAG_RECESSED_TAILLIGHT_CORONAS
FLAG_REPORT_CRIME_IF_STANDING_ON
* FLAG_RICH_CAR
* FLAG_SMALL_WORKER
* FLAG_SPAWN_BOAT_ON_TRAILER
* FLAG_SPAWN_ON_TRAILER
* FLAG_SPORTS
* FLAG_SPRAY_PETROL_BEFORE_EXPLOSION
* FLAG_TALL_SHIP
* FLAG_TWO_DOORS_ONE_SEAT
* FLAG_USE_COVERBOUND_INFO_FOR_COVERGEN
* FLAG_USE_FAT_INTERIOR_LIGHT
* FLAG_USE_FIVE_ANIM_THROW_FP
* FLAG_USE_FULL_ANIMS_FOR_MP_WARP_ENTRY_POINTS
* FLAG_USE_HIGHER_DOOR_TORQUE
* FLAG_USE_LIGHTING_INTERIOR_OVERRIDE
* FLAG_USE_PILOT_HELMET
* FLAG_USE_RESTRICTED_DRIVEBY_HEIGHT
* FLAG_USE_SMALLER_OPEN_DOOR_RATIO_TOLERANCE
* FLAG_USE_STEERING_PARAM_FOR_LEAN
* FLAG_USE_STRICTER_EXIT_COLLISION_TESTS
* FLAG_USE_WEAPON_WHEEL_WITHOUT_HELMET
* FLAG_USE_TURRET_RELATIVE_AIM_CALCULATION

### 1.59. type
* Vehicle type.

Available types:

* VEHICLE_TYPE_BICYCLE
* VEHICLE_TYPE_BIKE
* VEHICLE_TYPE_BLIMP
* VEHICLE_TYPE_BOAT
* VEHICLE_TYPE_CAR
* VEHICLE_TYPE_HELI
* VEHICLE_TYPE_PLANE
* VEHICLE_TYPE_SUBMARINE
* VEHICLE_TYPE_TRAILER
* VEHICLE_TYPE_TRAIN
* VEHICLE_TYPE_QUADBIKE

### 1.60. plateType

Determines whether the vehicle has plates and where they're mounted.

* VPT_BACK_PLATES
* VPT_FRONT_PLATES
* VPT_FRONT_AND_BACK_PLATES
* VPT_NONE

### 1.61. dashboardType

* The type of the vehicle dashboard. 

Example: <dashboardType>VDT_TAILGATER</dashboardType>

### 1.62. vehicleClass

* The vehicle class. Displayed when entering the vehicle.

Available classes:

* VC_SPORT
* VC_COUPE
* VC_EMERGENCY
* VC_INDUSTRIAL
* VC_COMMERCIAL
* VC_SEDAN
* VC_PLANE
* VC_UTILITY
* VC_SUV
* VC_SUPER
* VC_IMUSCLE
* VC_COMPACT
* VC_VAN
* VC_SPORT_CLASSIC
* VC_OFF_ROAD
* VC_MILITARY
* VC_SERVICE
* VC_CYCLE
* VC_MOTORCYCLE
* VC_HELICOPTER
* VC_BOAT
* VC_RAIL

### 1.63. wheelType

* The TYPE of wheels the vehicle uses by default.

Available types:

* VWT_BIKE
* VWT_HIEND
* VWT_LOWRIDER
* VWT_MUSCLE
* VWT_OFFROAD
* VWT_SPORT
* VWT_SUV
* VWT_TUNER


### 1.64. trailers

* Determines what trailers it can spawn towing. 
* Use the trailer's model name.

### 1.65. additionalTrailers
### 1.66. drivers
* Determines the ped who can be found driving the vehicle. Use the ped's model name.

### 1.67. extraIncludes
### 1.68. doorsWithCollisionWhenClosed
### 1.69. driveableDoors
### 1.70. bumpersNeedToCollideWithMap value
### 1.71. needsRopeTexture value
### 1.72. requiredExtras
### 1.73. rewards
* Reward the player with something (a weapon) when entering the vehicle 
* Defined by pickups.meta.
### 1.74. cinematicPartCamera

Used values: 

<Item>WHEEL_FRONT_RIGHT_CAMERA</Item>
<Item>WHEEL_FRONT_LEFT_CAMERA</Item>
<Item>WHEEL_REAR_RIGHT_CAMERA</Item>
<Item>WHEEL_REAR_LEFT_CAMERA</Item>
<Item>WHEEL_WIDE_REAR_RIGHT_CAMERA</Item>
<Item>WHEEL_WIDE_REAR_LEFT_CAMERA</Item>
<Item>BICYCLE_WHEEL_REAR_LEFT_CAMERA</Item>
<Item>BICYCLE_WHEEL_REAR_RIGHT_CAMERA</Item>
<Item>HELI_REAR_ROTOR_CAMERA</Item>
<Item>CARGOBOB_RIGHT_REAR_ROTOR_CAMERA</Item>
<Item>CARGOBOB_LEFT_REAR_ROTOR_CAMERA
<Item>WINGTIP_LEFT_CAMERA</Item>
<Item>WINGTIP_RIGHT_CAMERA</Item>
<Item>CUBAN_TAIL_LEFT_CAMERA</Item>
<Item>CUBAN_TAIL_RIGHT_CAMERA</Item>
<Item>DUSTER_WINGTIP_LEFT_CAMERA</Item>
<Item>DUSTER_WINGTIP_RIGHT_CAMERA</Item>
<Item>PLANE_TAIL_LEFT_CAMERA</Item>
<Item>PLANE_TAIL_RIGHT_CAMERA</Item>
<Item>MAMMATUS_WINGLIGHT_LEFT_CAMERA</Item>
<Item>MAMMATUS_WINGLIGHT_RIGHT_CAMERA</Item>
<Item>WINGLIGHT_LEFT_CAMERA</Item>
<Item>WINGLIGHT_RIGHT_CAMERA</Item>
<Item>TITAN_WINGLIGHT_LEFT_CAMERA</Item>
<Item>TITAN_WINGLIGHT_RIGHT_CAMERA</Item>
<Item>TITAN_TAIL_LEFT_CAMERA</Item>
<Item>TITAN_TAIL_RIGHT_CAMERA</Item>
<Item>CARGOPLANE_WINGTIP_LEFT_CAMERA</Item>
<Item>CARGOPLANE_WINGTIP_RIGHT_CAMERA</Item>
<Item>MARQUIS_SIREN_LEFT_CAMERA</Item>
<Item>MARQUIS_SIREN_RIGHT_CAMERA</Item>
<Item>DINGHY_WINDSCREEN_RIGHT_CAMERA</Item>
<Item>DINGHY_WINDSCREEN_LEFT_CAMERA</Item>
<Item>VEH_HANDLEBAR_LEFT_CAMERA</Item>
<Item>VEH_HANDLEBAR_RIGHT_CAMERA</Item>
<Item>VEH_WINDOW_FRONT_LEFT_CAMERA</Item>
<Item>VEH_WINDOW_FRONT_RIGHT_CAMERA</Item>

### 1.75. NmBraceOverrideSet
### 1.76. buoyancySphereOffset
### 1.77. buoyancySphereSizeScale
### 1.78. pOverrideRagdollThreshold
* Seems to be used in Rhino and Dozer.
### 1.79. firstPersonDrivebyData

---

#### This thread is not 100% completed. Please help me to complete it.

Thanks for everyone who have helped.

Thanks for reading. :)