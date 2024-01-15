# Getting up to speed with scripting for GTA V

So you wanna create your first GTA V script? There's a few things to think of and know beforehand, which helps you in making a script. This post will quickly explain what your options are, what you already need to do beforehand, and link some existing guides.

You do not need to be an expert at programming, since scripting in games can be a very fun way to learn a language and some concepts.

## Useful skills and tools to have

* [Knowing how to install and play with mods](https://forums.gta5-mods.com/topic/14693/quick-start-guide-to-modding-grand-theft-auto-v)
* Some programming basics
* Some IDEs to develop in, such as Visual Studio
* Information resources:
  * [Natives (by alloc8or, updated)](https://alloc8or.re/gta5/nativedb/)
  * [Natives (FiveM, updated, also lists old names)](https://runtime.fivem.net/doc/natives/)
  * [Natives (ScriptHookV, older)](http://www.dev-c.com/nativedb/)
  * [Scaleforms](https://www.vespura.com/fivem/scaleform/)
  * [Animations](https://alexguirre.github.io/animations-list/)
  * [Decompiled scripts](https://github.com/root-cause/v-decompiled-scripts)
  * [Particle effects](https://particles.altv.mp/)

## Scripting frameworks

There are different frameworks (libraries) that you can make scripts for. These manage loading scripts into the game for you, and provide functions to interact with the game.

| Scripting framework | Language | Features/Notes |
|---------------------|----------|----------------|
| [ScriptHookV](https://www.dev-c.com/gtav/scripthookv/) | C++ | Barebones scripting interface, decently popular, standalone |
| [ScriptHookVDotNet](https://github.com/crosire/scripthookvdotnet/releases) | C#/.NET languages | Powerful scripting interface, very popular, builds on ScriptHookV |
| [RagePluginHook](https://ragepluginhook.net/) | C#/.NET languages | Powerful scripting interface, not as popular, standalone |

There are other similar frameworks, standalone or requiring ScriptHookV, with their own advantages and disadvantages. I will not go into FiveM in this quick overview, but there's good support for many languages there too.

Generally, as a script developer, you want to choose something that allows you to develop in an easy way, or where the learning curve isn't as steep. Depending on your experience with software development and/or any performance requirements, you may choose your scripting framework. It's a good idea to give them all a quick spin.

## Scripting

Scripting is basically programming. This chapter will discuss some GTA 5-specific details.

### Structure

Scripts are generally run in an infinite loop. Each iteration here is called a "tick", in which it should have completed all its operations for that tick. If you've ever developed for an Arduino or something alike, you might already be familiar with the process.

Depending on your framework, you need to manually make that loop, or you can just use a provided function like `OnTick()`. All of your script logic is run in that loop, and at the end you instruct your script to wait until its turn happens again. If your framework offers a "Tick" mechanism, this manual wait is not needed, and you can set the tick rate elsewhere.

Before the loop starts, you can add some initialization code. For example: read your settings.

### Natives

To interact with the game, you can use natives. These are essentially the functions Rockstar also uses in their game scripts to interact with the world. The scripting frameworks find these natives and provide them to you. Internally, these frequently change when the game is updated, but the scripting framework will also be updated to keep the natives the same to you.

There are many natives for many different operations, ranging from player functions to various UI functions. All these natives have a C-interface, meaning they are simply functions, sometimes with a return value, sometimes with arguments. You can make wrappers for these to interact with the game in an object-oriented manner, or use a framework that does this heavy lifting for you. ScriptHookV is very barebones and does not wrap any of these natives, ScriptHookVDotNet and RagePluginHook do abstract this away for you. The latter two still provide functions to directly call the natives, so you have full control regardless of which framework you pick.

Some natives can be run once and have a lasting effect, others need to be run every tick. Use one of the Native DBs or your framework documentation to find out which natives behave in which way.

In general, beware of the exact workings of these natives. As everything here is unofficial and has been discovered with reverse engineering and trial-and-error, documentation might not be very complete and many natives are still unnamed. Expect some trial-and-error when using less straightforward natives.

### User interaction

Depending on your use case, there are different ways to get your user interacting with your mod. Some use cases do not require the user to do anything, and integrate right into the existing aspects of the game. Others might require some explicit user input, in form of a command, or through some sort of menu.

Again, how this is implemented depends on your chosen framework, but generally these methods can be put into a few categories. These are not exclusive, and depending on how complex you want to make your mod, mixing these is certainly possible.

**No** input can be used for things that should "run in the background", such as a god mode or vehicle auto-repair.

**Keypresses** can be used to activate a function, or combine game actions with additional mod enhancements. You have two options here.

1. Detect key presses and controller input with Windows APIs. This does not use any game mapping but might be useful when trying to set consistent or inaccessible keys for the game.
2. Respond to input by using a game native. This uses the same controls that the game sees. It's also the easier way to respond to both controller and keyboard input.

**Commands**

GTA V on PC comes with a cheat console. By pressing tilde (~) this opens, and text can be entered. With natives it's possible to respond to this input once the player has finished their input. It's also possible to launch new text entry windows.

Additionally, RagePluginHook and ScriptHookVDotNet v3 support consoles of their own, though these can generally be considered as tools to aid development.

**Menus**

The game does not offer any native-accessible menus, such as the interaction menu or tuning menus. You'll need to spin up your own, or use an existing library.

* [NativeUI for ScriptHookVDotNet](https://github.com/Guad/NativeUI/releases/)
* [RAGENativeUI for RagePluginHook](https://github.com/alexguirre/RAGENativeUI/releases) (NativeUI port)
* ScriptHookV has various menu bases, with most taking inspiration from the included trainer.
  * [NativeTrainer sample in ScriptHookV SDK](https://www.dev-c.com/gtav/scripthookv/)
  * [GTAVMenuBase for ScriptHookV](https://github.com/E66666666/GTAVMenuBase)

Making your own can take a lot of effort, so most scripts that use a menu stick with an existing base.

## Further reading and Resources

[AHK1221](https://forums.gta5-mods.com/user/ahk1221)'s tutorials. (Text & images, ScriptHookVDotNet)

* [Part 1](https://forums.gta5-mods.com/topic/6282/net-c-shvdn-modding-basics-and-how-to-start-modding-in-c-part-1)
* [Part 2](https://forums.gta5-mods.com/topic/6442/net-c-shvdn-modding-basics-what-is-ontick-part-2)
* [Part 3](https://forums.gta5-mods.com/topic/7113/net-c-shvdn-modding-basics-vector3s-and-vehicles-manipulation-part-3)


[Metiri Personal](https://www.youtube.com/channel/UCMdBeKmopZBdd3-1n5lOjhA)'s tutorials (YouTube videos, ScriptHookVDotNet)

* [Playlist](https://www.youtube.com/watch?v=PaQZEdES7No&list=PLbhQKmLHe3WVkQx1oO3XZuGcfk0ddzlUt)

[Alexander Blade](https://www.dev-c.com/gtav/scripthookv/)'s ScriptHookV SDK samples (Code)

* [GTAForums topic on ScriptHookV](https://gtaforums.com/topic/788343-script-hook-v/)
* [GTAForums topic on native research](https://gtaforums.com/topic/717612-v-scriptnative-documentation-and-research/)

General information/support channels:

* [GTA5-Mods Discord](https://discordapp.com/invite/HW9bD8k)
* [GTAForums coding subforum](https://gtaforums.com/forum/372-coding/)

Suggestions are welcome!

# Disclaimer, more info

This is purely an overview of what scripting for GTA V is and where to find resources. I do not claim to know everything about scripting - I felt a central place for people to start with scripting, to lack. Suggestions are welcome to fill in information gaps or correct wrong information.

I'm aware information about MP mods such as FiveM, RageMP and whatnot are missing, but the platforms themselves should already provide plenty of guidance. I don't know much about these, so I left them out.

I made this guide a while ago on [GitHub (gists)](https://gist.github.com/E66666666/0678311d913a348bc4fcae0751436a48), but only really published it now. You can find the changelog of the guide there.