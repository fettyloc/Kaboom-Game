# Kaboom Platformer Remix

Hi! This is a simple mario-like platformer game using [Kaboom.js](https://kaboomjs.com/). To learn the basics of Kaboom, you can also create a [Kaboom Template](https://replit.com/@replit/Kaboom) and follow the tutorial on the right side pane, or follow the stand-alone tutorial [here](https://kaboomjs.com/doc/intro).

## Run the game first

Before playing around the code, try running the game first! This is a simple 2 level mario-like platformer. Scan through the code and see if you can figure out what's happening.

## 1. Customize the Levels

Kaboom uses a very simple ascii-art style level builder that looks like this:

> the following code block might require resizing the instruction pane to view correctly

```js
const LEVELS = [
	[
		"                          $",
		"                          $",
		"                          $",
		"                          $",
		"                          $",
		"           $$         =   $",
		"  %      ====         =   $",
		"                      =   $",
		"                      =    ",
		"       ^^      = >    =   @",
		"===========================",
	],
	[
		"     $    $    $    $     $",
		"     $    $    $    $     $",
		"                           ",
		"                           ",
		"                           ",
		"                           ",
		"                           ",
		" ^^^^>^^^^>^^^^>^^^^>^^^^^@",
		"===========================",
	],
]
```

Here is what defines what each symbol means:

```js
// define what each symbol means in the level graph
const levelConf = {
	// grid size
	width: 64,
	height: 64,
	// define each object as a list of components
	"=": () => [
		sprite("grass"),
		area(),
		solid(),
		origin("bot"),
	],
	"$": () => [
		sprite("coin"),
		area(),
		pos(0, -9),
		origin("bot"),
		"coin",
	],
	"%": () => [ /* components for % */ ],
	"^": () => [ /* components for ^ */ ],
	"#": () => [ /* components for # */ ],
	">": () => [ /* components for > */ ],
	"@": () => [ /* components for @ */ ],
}
```

Try edit these ASCII levels, draw some new blocks, add some more coins and challenges, or even add new levels by adding to the `LEVELS` array

## 2. Change the Sprites

Currently the game is using Kaboom's default sprites. 

Currently all blocks are `64x64` pixels in size, you can also use another size if you change the `width` and `height` in `levelConf`

The sprites are loaded at the top of the file

```js
loadSprite("bean", "sprites/bean.png")
loadSprite("ghosty", "sprites/ghosty.png")
loadSprite("spike", "sprites/spike.png")
loadSprite("grass", "sprites/grass.png")
loadSprite("prize", "sprites/jumpy.png")
```

If you have your own custom sprites ready, try replacing these

## 3. Add New Mechanics

If you're feeling creative try adding some new mechanics! What about some new enemy types? What about some new sort of power ups? What about some more challenging levels? 