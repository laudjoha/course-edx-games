
# Pong

## Important Fuctions

From Pong-0

**Love.load()**

Used for initializing game state at the very beginning of program execution

**love.update(dt)**

Called each frame by LÖVE; dt will be the elapsed time in seconds since the last frame. We can use this to scale any changes in our game for even behavior across framerates.

**love.draw()**

Called each frame by LÖVE after update for drawing things to the screen once they've changed.

LÖVE2D expects these functions to be implemented in main.lua and calls them internally; if we don't define them, it will still function, but our game will be fundamentally incomplete, at least if update or draw are missing!

**love.graphics.printf(text, x, y, [width], [align])**

versatile print function that can align text left, right, or center on the screen

**love.window.setMode(width, height, params)**

Used to initialize the window's dimensions and to set parameters like vsync (vertical sync), whether we're fullscreen or not, and whether the window is resizable after startup. Won't be using past this example in favor of the push virtual resolution library, which has its own method like this, but useful to know if encountered in other code.

---

From Pong-1

**love.graphics.setDefaultFilter(main, mag)**

Sets the texture scaling filter when minimizing and magnifying textures and fonts; default is bilinear, which causes bluriness, and for our use cases we will typically want nearest-neighbor filtering('nearest'), which results in perfect pixel upscaling and downscaling, simmulating a retro feel.

**love.keypressed(key)**

A LÖVE2D callback function that executes whenever we press a key, assuming we've implemented this in our main.lua, in the same vein as love.load(), love.update(dt), and love.draw().

**love.event.quit()**

Simple function that terminates the application.

---

From Pong-2

**love.graphics.newFont(path, size)**

Loads a font file into memory at a specific path, setting it to a specific size, and storing it in an object we can use to globally change the currently active font that LÖVE2D is using to render text (functioning like a state machine).

**love.graphics.setFont(font)**

Sets LÖVE2D currently active font (of which there can only be one at a time) to a passed-in font object that we can create using love.graphics.newFont.

**love.graphics.clear(r, g, b, a)**

Wipes the entire screen with a color defined by an RGBA set, each component being from 0-255.

**love.graphics.rectangle(mode, x, y, width, height)**

Draws a rectangle onto the screen using whichever our active color is ( love.graphics.setColor, which we don't need to use in this particular project since most everything is white, the default LÖVE2D color ). mode can be set to 'fill', or 'line', which results in a filled or outlined rectangle, respectively, and the other four parameters are its position and size dimensions. This is the cornerstone drawing function of the entirety of our Pong implementation!

---
