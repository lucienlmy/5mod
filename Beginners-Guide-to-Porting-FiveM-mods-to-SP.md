Over the last year we have seen a surge in FiveM activity on 5mods. This is fine, as FiveM mods are allowed, provided they come with a valid SinglePlayer install (see [Updated author rules and regulations](https://forums.gta5-mods.com/topic/23971/updated-author-rules-and-regulations))

A SinglePlayer install, though -- especially when dealing with resources originally meant for FiveM -- often requires reformatting to a structure SP can understand, aka a proper DLC. Here is where things often start to fall apart, as many FiveM modders (no offense) tend to have no clue how SP works. The result is mostly a very unsatisfactory set of installation instruction, ranging from "Drop the files into your usual resources folder!" to totally bogus directions to install a DLC (often copied from just a random page), while the content consists soley of a single ymap (or, worse, just a lua stream folder).  On the latter I can be quick: we always check, so trying to pull a fast one on us is kinda pointless, and a certified way to get your mod Rejected.

Then there are, of course, FiveM players who honestly try, but simply do not (fully) understand the process. So, this will be a small tutorial, especially for the FiveM uploaders crowd, to give you an idea how to properly port your FiveM mods to SinglePlayer content. At the end of this post will be a full, generic template for a proper content.xml and setup2.xml file for a DLC. I will piecemeal things a bit. Pay close attention to the flags used. Also, keep in mind that a DLC can become endlessly more complicated than this; but with this simple template, you should be able to avoid the most egregious common errors.

    		<Item>
    			<filename>dlc_template:/%PLATFORM%/levels/gta5/my_assets.rpf</filename>
    			<fileType>RPF_FILE</fileType>
    			<overlay value="false" />
    			<disabled value="true" />
    			<persistent value="false" />
    		</Item>

This is where your OWN props go (.ydr/ytd files).

    		<Item>
    			<filename>dlc_template:/%PLATFORM%/levels/gta5/my_overrides.rpf</filename>
    			<fileType>RPF_FILE</fileType>
    			<overlay value="true"/>
    			<disabled value="true" />
    			<persistent value="false" />
    		</Item>

This is where existing GAME props go that need to be overriden (edited building .ydr files and such).

    		<Item>
    			<filename>dlc_template:/%PLATFORM%/levels/gta5/my_metadata.rpf</filename>
    			<fileType>RPF_FILE</fileType>
    			<overlay value="true" />
    			<disabled value="true" />
    			<persistent value="true" />
    		</Item>

This RPF is reserved for your ymaps, _manifest, and .ybn files -- INCLUDING the ones that are meant to override game files. This is especially pertinent to FiveM uploaders, who tend to just lump everything together. Like, say, you edited dt1_07_0.ybn (a game collision file); then you would put your own dt1_07_0.ybn in here, so the game wil start to use yours instead!

As for setup2.xml, pay particular attention to:

   	<order value="71" />

Choose a high enough number, so the game will load your DLC last (or, at least, after the game's own DLC's).

You can also disable an obnoxious ybn outright:

    <filesToInvalidate>
        <Item>dt1_07_0.ybn</Item>
    </filesToInvalidate>

And other game files:

    <filesToInvalidate>
        <Item>update:/dlc_patch/mpheist/%PLATFORM%/levels/gta5/_citye/hollywood_01/hollywood_metadata.rpf</Item>
    </filesToInvalidate>

Or a specific interior:

    <filesToInvalidate>
        <Item>hei_hw1_blimp_interior_29_dlc_apart_high2_new_milo_.interior</Item>
    </filesToInvalidate>

Then there's also overlayinfo.meta, but that's maybe for a later date. This should carry you quite the stretch, though.

------
CONTENT.XML

    <?xml version="1.0" encoding="utf-8"?>
    <CDataFileMgr__ContentsOfDataFileXml>
    	<disabledFiles />
    	<includedXmlFiles />
    	<dataFiles>
    		<Item>
    			<filename>dlc_template:/%PLATFORM%/levels/gta5/my_assets.rpf</filename>
    			<fileType>RPF_FILE</fileType>
    			<overlay value="false" />
    			<disabled value="true" />
    			<persistent value="false" />
    		</Item>
    		<Item>
    			<filename>dlc_template:/%PLATFORM%/levels/gta5/my_overrides.rpf</filename>
    			<fileType>RPF_FILE</fileType>
    			<overlay value="true"/>
    			<disabled value="true" />
    			<persistent value="false" />
    		</Item>
    		<Item>
    			<filename>dlc_template:/%PLATFORM%/levels/gta5/my_metadata.rpf</filename>
    			<fileType>RPF_FILE</fileType>
    			<overlay value="true" />
    			<disabled value="true" />
    			<persistent value="true" />
    		</Item>
    	</dataFiles>
    	<contentChangeSets>
    		<Item>
    			<changeSetName>template_AUTOGEN</changeSetName>
    			<mapChangeSetData />
    			<filesToInvalidate />
    			<filesToDisable />
    			<filesToEnable>
    				<Item>dlc_template:/%PLATFORM%/levels/gta5/my_assets.rpf</Item>
    				<Item>dlc_template:/%PLATFORM%/levels/gta5/my_overrides.rpf</Item>
    			</filesToEnable>
    			<txdToLoad />
    			<txdToUnload />
    			<residentResources />
    			<unregisterResources />
    			<requiresLoadingScreen value="false" />
    		</Item>
    		<Item>
    			<changeSetName>template_STREAMING_MAP</changeSetName>
    			<mapChangeSetData>
    				<Item>
    					<associatedMap>MO_JIM_L11</associatedMap>
    					<filesToInvalidate />
    					<filesToDisable />
    					<filesToEnable>
    						<Item>dlc_template:/%PLATFORM%/levels/gta5/my_metadata.rpf</Item>
    					</filesToEnable>
    					<txdToLoad />
    					<txdToUnload />
    					<residentResources />
    					<unregisterResources />
    				</Item>
    			</mapChangeSetData>
    			<requiresLoadingScreen value="true" />
    			<loadingScreenContext>LOADINGSCREEN_CONTEXT_LAST_FRAME</loadingScreenContext>
    			<useCacheLoader value="true" />
    		</Item>
    	</contentChangeSets>
    	<patchFiles />
    </CDataFileMgr__ContentsOfDataFileXml>
    
SETUP2.XML

    <?xml version="1.0" encoding="UTF-8"?>
    <SSetupData>
    	<deviceName>dlc_template</deviceName>
    	<datFile>content.xml</datFile>
    	<timeStamp>01/12/2020 00:00</timeStamp>
    	<nameHash>template</nameHash>
    	<contentChangeSets />
    	<contentChangeSetGroups>
    		<Item>
    			<NameHash>GROUP_STARTUP</NameHash>
    			<ContentChangeSets>
    				<Item>template_AUTOGEN</Item>
    			</ContentChangeSets>
    		</Item>
    		<Item>
    			<NameHash>GROUP_MAP</NameHash>
    			<ContentChangeSets>
    				<Item>template_STREAMING_MAP</Item>
    			</ContentChangeSets>
    		</Item>
    		<Item>
    			<NameHash>GROUP_MAP_SP</NameHash>
    			<ContentChangeSets>
    				<Item>template_STREAMING_MAP</Item>
    			</ContentChangeSets>
    		</Item>
    	</contentChangeSetGroups>
    	<startupScript />
    	<scriptCallstackSize value="0" />
    	<type>EXTRACONTENT_COMPAT_PACK</type>
    	<order value="71" />
    	<minorOrder value="0" />
    	<isLevelPack value="false" />
    	<dependencyPackHash />
    	<requiredVersion />
    	<subPackCount value="0" />
    </SSetupData>