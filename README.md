#forge-clj: Clojure in Minecraft

##Description

A WIP implementation of Clojure working with Minecraft Forge. This is now somewhat useable!

Explaining everything here would be a hassle, so go look at the [test-mod](https://github.com/yoshiquest/test-mod "test-mod") I made. It assumes you already know Clojure for some things. I plan on making a separate tutorial on Clojure itself and using it with forge-clj later though.

##Usage (for users)

Simply download the latest version of forge-clj, as well as the mod you want to run, and put them both in the mods folder.

##Usage (for modders)

First off, set up Forge as normal. Then download the latest version of the forge-clj dev kit, and extract its contents into the dev environment. Afterwords, be sure to rename the things in the build.gradle to use your package names and not mine.

If this doesn't work be sure to tell me so I can fix it.

Oh yeah, when getting ready to deploy your mod, be sure to use gradle build (not runclient!) first. For some reason the jar generated by runclient is broken, and the one generated by build isn't.

##Downloads

- Version 0.4.0: [forge-clj](http://bit.ly/1GREpCN "forge-clj Version 0.4.0") [forge-clj devkit](http://bit.ly/1GREqXl "forge-clj devkit Version 0.4.0")

- Version 0.3.0: [forge-clj](http://bit.ly/1OJ2P3H "forge-clj Version 0.3.0") [forge-clj devkit](http://bit.ly/1MTJhbc "forge-clj devkit Version 0.3.0")

- Version 0.2.2: [forge-clj](http://bit.ly/1NCq8vM "forge-clj Version 0.2.2") [forge-clj devkit](http://bit.ly/1jsIHFC "forge-clj devkit Version 0.2.2")

- Version 0.2.1: [forge-clj](http://bit.ly/1WOmksN "forge-clj Version 0.2.1") [forge-clj devkit](http://bit.ly/1LmEj1n "forge-clj devkit Version 0.2.1")

- Version 0.2.0: [forge-clj](http://bit.ly/1FTJ5HO "forge-clj Version 0.2.0") [forge-clj devkit](http://bit.ly/1jOENra "forge-clj devkit Version 0.2.0")

##Changelog

- Version 0.4.0: Added a very large system for rendering models. Currently only works for tile entities, and techne isn't supported (yet). Also added a few more minor things, such as the ability to create your own creative tab. Finally, I entirely revamped the organization of the mod, by splitting it into parts. Both forge-clj and test-mod are far easier to read now that everything isn't just in a single file. As a sidenote, as of this version I've started to use a custom program to help me auto-distribute each new version. Hopefully this means that new versions will be coming out faster than normal, since it won't be as much work for me.

- Version 0.3.0: Added a multitude of systems. First off, the Tile Entity system was revamped, and the data is now stored inside an atom within the class instance rather than a global atom. This new class also supports hash-map-like syntax for getting and setting values. Next, I added the ability to create custom packets. The system takes data as a map, converts it to nbt, and sends it using the network system implemented. I then added the ability to create an event handler. You specify the name as a keyword, and the event Class itself in the :event tag. Finally, I added the ability to add custom entity properties, using a similar system to that of the Tile Entities.

- Version 0.2.2: This update focuses on Tile Entities and NBT data. First, you now have the ability to create Tile Entities. Note that for Tile Entities, a CLASS is generated, rather than an instance like normal, so it'll be a bit different to work with. Next, I added the ability to convert Minecraft's NBT data into a Clojure map and back. Finally, I added a system that will automatically store this converted nbt data in an atom of your choice, using a unique key underneath in order to separate the instances.

- Version 0.2.1: Improved the defx (defblock, defitem, etc.) macros. Instead of being the same thing over and over again, I now have a defobj macro that they all use instead. I also removed the field functions (creative-tab, step-sound, etc.), since they were pretty redundent, were a pain to make and maintain, and the amound of code needed by the user really didn't change. Just use java interop instead. I also merged the register-generator function with the rest of the register functions, so now you only need to call 1 function again.

- Version 0.2.0: Even more changes now. I've been using BedrockMiner's tutorials to know what I need to implement, and I'm proud to say that all of the basic tutorials (except for potions) can be done in forge-clj (and most have been done within the testmod as well). It works pretty well now, though some refactoring needs to be done, especially with the defx macros. I also separated the dev and user version, because apparantly you can do that. Things such as metablocks/items, tools, food, armor, and basic world generation were added. Also added a download link now.

- Version 0.1.0: Lots of changes here: First, I added a working proxy system, to allow for client and common proxies. Second, I separated the test mod and forge-clj, so now they work independently. Finally, I fixed the ability to access certain fields (like creative-tab and sound-type), so that they work both in the dev environment and in a normal minecraft installation.

- Version 0.0.1: Initial Commit

##License

Copyright © 2015 Ryan Haney (Yoshiquest)

Distributed under the Eclipse Public License either version 1.0 or (at
your option) any later version.
