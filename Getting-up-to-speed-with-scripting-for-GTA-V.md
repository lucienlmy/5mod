# Getting up to speed with scripting for GTA V

This article contains some useful information to get started when creating your first GTA V script.
Your options, things you need to prepare, and other guides are listed in this article.

You don't need to be proficient at programming: scripting in games can be a fun way to learn a language and programming concepts.

## Useful skills and tools to have

* [General knowledge on using mods](https://github.com/5mods/tutorials/wiki/Quick-start-overview-of-modding-Grand-Theft-Auto-V)
* Basic programming knowledge
* A development environment, such as [Visual Studio](https://visualstudio.microsoft.com/)
* Information resources:
  * Natives (functions to interact with the game)
    * [alloc8or's Native DB](https://alloc8or.re/gta5/nativedb/)
    * [Dot.'s Native DB](https://nativedb.dotindustries.dev/natives) 
    * [FiveM's Native DB](https://runtime.fivem.net/doc/natives/)
    * [ScriptHookV's Native DB (outdated)](http://www.dev-c.com/nativedb/)
  * [Decompiled scripts](https://github.com/root-cause/v-decompiled-scripts)
  * [Scaleforms](https://www.vespura.com/fivem/scaleform/)
  * [Animations](https://alexguirre.github.io/animations-list/)
  * [Particle effects](https://particles.altv.mp/)

## Scripting frameworks

Multiple frameworks (libraries) exist that you can make scripts for. These manage loading scripts into the game for you, and provide functions to interact with the game.

| Scripting framework | Language | Features/Notes |
|---------------------|----------|----------------|
| [ScriptHookV](https://www.dev-c.com/gtav/scripthookv/) | C++ | Barebones scripting interface, widely used, standalone |
| [ScriptHookVDotNet](https://github.com/crosire/scripthookvdotnet/releases) | C#/.NET languages | Powerful scripting interface, very widely used, relies on ScriptHookV |
| [RagePluginHook](https://ragepluginhook.net/) | C#/.NET languages | Powerful scripting interface, less commonly used, standalone |
| [Lua Plugin](https://www.gta5-mods.com/tools/jm36-lua-plugin-for-script-hook-v-reloaded) | Lua | New FiveM-style Lua for SP |

There are other similar frameworks, standalone or requiring ScriptHookV, with their own advantages and disadvantages. This article does not cover FiveM, but FiveM has great support for scripting and many resources.

As a script developer, there is no best choice. It's best to start out with something that you're somewhat familiar with, or choose something with a good learning curve. It's a good idea to give them all a try before settling on one (though a .NET language or Lua is recommended for complete beginners, as C++ can get quite challenging when you start running into issues).

## Scripting

When you develop scripts for GTA V, your main interaction will be with the game script engine. Scripting here means programming while interacting with the game. It's still programming, but against what GTA V and your framework has to offer. This section discusses GTA V specifics.

### Structure

Scripts are generally run in an infinite loop. Each iteration here is called a "tick", in which it should have completed all its operations for that tick. If you've ever developed for an Arduino or something like that, you might already be familiar with the process.

Depending on your framework, you need to manually make that loop, or you can just use a provided function like `OnTick()`. All of your script logic is run in that loop, and at the end you instruct your script to wait until its turn happens again. If your framework offers a "Tick" mechanism, this manual wait is not needed, and you can set the tick rate elsewhere.

Before the loop starts, you can add some initialization code. For example: read your settings.

### Natives

To interact with the game, you can use natives. These are essentially the functions Rockstar also uses in their game scripts to interact with the game world. The scripting frameworks find and provide these natives for you. Internally, these frequently change when the game is updated, but the scripting framework also gets updated to keep the natives the same to you, so your script does not need an update every time the game updates.

Many natives exist for many different operations, ranging from player functions to various UI functions. These natives have a C-interface, meaning they are simply functions, sometimes with a return value, sometimes with arguments. You can make wrappers for these to interact with the game in an object-oriented manner, or use a framework that does this heavy lifting for you. ScriptHookV is very barebones and does not wrap any of these natives, ScriptHookVDotNet and RagePluginHook do abstract this away for you. The latter two still provide functions to directly call the natives, so you have full control regardless of which framework you pick.

Some natives can be run once and have a lasting effect, others need to be run every tick. Use one of the Native DBs or your framework documentation to find out which natives behave in which way.

In general, beware of the exact workings of these natives. As everything here is unofficial and has been discovered with reverse engineering and trial-and-error, documentation might not be completely accurate. Expect some trial-and-error when using less straightforward natives.

Some things may not be accessible through natives, for these you need to reverse things or re-use things libraries offer. Libraries like ScriptHookVDotNet and RagePluginHook offer a good amount of these advanced non-native functionalities, but this may not be compatible when Rockstar significantly updates the game.

### User interaction

Depending on your use case, there are different ways to get your user interacting with your mod. Some use cases do not require the user to do anything, and integrate right into the existing aspects of the game. Others might require some explicit user input, in form of settings, commands, or through some sort of UI or menu.

Again, how this is implemented depends on your chosen framework, but generally these methods can be put into a few categories. These are not exclusive, and depending on how complex you want to make your mod, mixing these is certainly possible.

**No** input can be used for things that run in the background, such as a god mode or vehicle auto-repair.

**Keypresses** can be used to activate a function, or combine game actions with additional mod enhancements. You have two options here.

1. Detect key presses and controller input with Windows APIs. This does not use any game mapping but might be useful when trying to set consistent or inaccessible keys for the game.
2. Respond to input by using a game native. This uses the same controls that the game sees. It's also the easier way to respond to both controller and keyboard input.

**Commands**

GTA V on PC comes with a cheat console. By pressing tilde (~) this opens, and text can be entered. With natives it's possible to respond to this input once the player has finished their input. It's also possible to launch new text entry windows.

Additionally, RagePluginHook and ScriptHookVDotNet v3 support consoles of their own, though these can generally be considered as tools to aid development.

**Menus**

The game does not offer any native-accessible menus, such as the interaction menu or tuning menus. You'll need to spin up your own, or use an existing library.

* ~~[NativeUI for ScriptHookVDotNet](https://github.com/Guad/NativeUI/releases/)~~ Superseded by LemonUI
* [LemonUI for ScriptHookVDotNet](https://www.gta5-mods.com/tools/lemonui)
* [RAGENativeUI for RagePluginHook](https://github.com/alexguirre/RAGENativeUI/releases) (NativeUI port)
* ScriptHookV has various menu bases, with most taking inspiration from the included trainer.
  * [NativeTrainer sample in ScriptHookV SDK](https://www.dev-c.com/gtav/scripthookv/)
  * [GTAVMenuBase for ScriptHookV](https://github.com/ikt32/GTAVMenuBase)

Making your own can take a lot of effort, so most scripts that use a menu stick with an existing base.

## Further reading and Resources

[Metiri Personal](https://www.youtube.com/channel/UCMdBeKmopZBdd3-1n5lOjhA)'s tutorials (YouTube videos, ScriptHookVDotNet)

* [Playlist](https://www.youtube.com/watch?v=PaQZEdES7No&list=PLbhQKmLHe3WVkQx1oO3XZuGcfk0ddzlUt)

[Alexander Blade](https://www.dev-c.com/gtav/scripthookv/)'s ScriptHookV SDK samples (Code)

* [GTAForums topic on ScriptHookV](https://gtaforums.com/topic/788343-script-hook-v/)
* [GTAForums topic on native research](https://gtaforums.com/topic/717612-v-scriptnative-documentation-and-research/)

General information/support channels:

* [GTA5-Mods Discord](https://discord.gg/2PR7aMzD4U) (Check the `#scripting` channel)
* [GTAForums coding subforum](https://gtaforums.com/forum/372-coding/)

Suggestions are welcome!

# Changelog

__2024-09-12__

* Remove defunct links
* Reword a few things

__2023-10-10__

* Add Dot.'s Native DB
* Add Lua Plugin
* Slight grammar/sentence updates 

__2020-05-21__

* Update native DB location to alloc8ors
* Add animations resource
* Add decompiled scripts resource

__2020-05-22__
* Updated scaleforms website

__2020-05-26__
* Add particles from Alt:V

__2020-07-02__

* Add FiveM Native DB