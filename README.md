# actormods
Automatically generate basic movement mods for actors using a simple input. This lets you move around sprites and such with simple [Mirin Template](https://github.com/XeroOl/mirin-template) ```set``` or ```ease``` calls without slamming a bunch of code into your mods.lua file. This won't let you do *everything*, but it should make it far easier for beginners to move stuff around if nothing else!

To use this, put ```actormods.xml``` inside the "plugins" folder of your modchart.

# Defining the Mods
You should call this function with curly braces.

```lua
actormods {actor, 'prefix'}
```
**actor** - the actor you want to add the mods to

**prefix** - a string to act as the prefix to all mods for that actor

You can do multiple at once to save space, like this:

```lua
actormods {actor1, 'prefix1', actor2, 'prefix2', actor3, 'prefix3'}
```

# Using The Mods
The plugin names all mods for an actor in a "prefix_modname" format. For example, if you do...
```lua
actormods{bg, 'background'}
```
...then to make the actor "bg" move, you would want to do...

```lua
ease {0, 6, inOutSine, 25, 'background_movex'}
```
Nothing stopping you from making the prefix the same as the actor, by the way, just make sure it's surrounded by ```'``` so it's a string.

# Mods supported
- movex
- movey
- movez
- zoom
- zoomx
- zoomy
- skewx
- skewy


# Plans 
- [ ] Support for other mods for opacity, tinting, etc
- [ ] Define mods for multiple actors in a single line
