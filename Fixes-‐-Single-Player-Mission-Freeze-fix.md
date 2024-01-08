Open your modded '**gameconfig.xml**' & reset the **MISSION** stack to default (**20500**) like below:

```xml
						<Item>
							<StackName>MISSION</StackName>
							<SizeOfStack value="20500"/>
							<NumberOfStacksOfThisSize value="1"/>
						</Item>
```

If this doesn't fix your mission freezing issue, first confirm that a vanilla 'gameconfig.xml' does indeed fix the issue & then follow a similar approach of defaulting parts of the 'gameconfig.xml' until you find the part that is breaking your game. Zero in on the exact parameter/s & reset it/them to vanilla.

That's it. Thought I would throw this one out there. Best of luck :thumbsup:

**Extra:** I also defaulted this parameter (below) while resetting the MISSION stack. I'm 99% sure the Mission stack was the only issue but just in case they both had a part to play I thought I would include this info (vanilla default for 'MULTIPLAYER_FREEMODE' stack is '42000' as below (it sits just above 'MISSION' stack in gameconfig). 
Reset it also if the 'MISSION' stack reset doesn't fix your problem on it's own :thumbsup:):

```xml
						<Item>
							<StackName>MULTIPLAYER_FREEMODE</StackName>
							<SizeOfStack value="42000"/>
							<NumberOfStacksOfThisSize value="1"/>
						</Item>
```
Sorry for being lazy & not confirming :slight_smile: You can safely default both parameters as I did if you like. I haven't had an issue with SP Missions since doing this (although I'm still relatively near the start of the game). Best of luck :thumbsup: