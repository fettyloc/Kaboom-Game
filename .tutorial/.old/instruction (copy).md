# Kaboom Platformer Remix
**Learning Goals**:
1. Learn what Kaboom is.
2. Understand the basic symbols used in Kaboom.
3. Customize the game.

**Time needed**: 30 mins

## What is Kaboom?
- Kaboom.js is a Replit created JavScript library that helps you build games fast.
- To learn the basics of Kaboom, follow the tutorial on the right side pane.
- You can also create a [Kaboom Template](https://replit.com/@replit/Kaboom) and follow or follow the stand-alone tutorial [here](https://kaboomjs.com/doc/intro).
- Kaboom uses a very simple ASCII-art style level builder. ASCII art is art created by a computer consisting of different characters.


## 1. Try the game first

- This is a simple 2 level mario-like platformer game. 
- Before changing any code, try running the game first!
- Click on `console` and then `cmd +s` to start the game.
- Can you figure out how to play?

## 2. Add another level

- Each character below represents a sprite (a stand alone computer graphic). For example, `=` is `grass`.
<details><summary>See the sprites here</summary>

```js
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
	"%": () => [
		sprite("prize"),
		area(),
		solid(),
		origin("bot"),
		"prize",
	],
	"^": () => [
		sprite("spike"),
		area(),
		solid(),
		origin("bot"),
		"danger",
	],
	"#": () => [
		sprite("apple"),
		area(),
		origin("bot"),
		body(),
		"apple",
	],
	">": () => [
		sprite("ghosty"),
		area(),
		origin("bot"),
		body(),
		patrol(),
		"enemy",
	],
	"@": () => [
		sprite("portal"),
		area({ scale: 0.5, }),
		origin("bot"),
		pos(0, -12),
		"portal",
	],
}
```
</details>

Add to the `LEVELS` array by copying what is between one set of `[ ],` to the top of the code right after the first opening brace `]`:

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

Using the sprites above, change the components of this new level: 

<details> <summary>It could look like this</summary>

```js
[
		"     $        $    $      $",
		"     $    #     $    %    $",
		"                           ",
		"                           ",
		"     =       =      =      ",
		"                           ",
		"                           ",
		" ^^^^>^^^^>^^^^>^^^^>^^^^^@",
		"===========================",
	],
```
</details>
  
Did you add more coins, prizes, spikes? The choice is yours!



## 2. Change the Sprites

Currently the game is using Kaboom's default sprites. 

Currently all blocks are `64x64` pixels in size, you can also use another size if you change the `width` and `height` in `levelConf`

The sprites are loaded at the top of the file.

```js
loadSprite("bean", "sprites/bean.png")
loadSprite("ghosty", "sprites/ghosty.png")
loadSprite("spike", "sprites/spike.png")
loadSprite("grass", "sprites/grass.png")
loadSprite("prize", "sprites/jumpy.png")
```

If you have your own custom sprites ready, try replacing these. Make sure you add the image to the `sprites` folder in your file tree too.

## 3. Add New Mechanics

### .onCollide(
Using 
```js
player.onCollide("sun", "earth", () => {
    addExplosion()
})
```
can you change `sun`, `earth` with another sprite the player could collide with to create an explosion? Maybe you add a new sprite?

## 4. Share your game!
### Don't be shy - the community loves it! 
1. ✅ Hit publish on top right, 
2. ✅ Give it a name, then hit Next
3. ✅ Add tags like #firstBuild #drawing, then hit Next
4. ✅ Upload an icon if you like, then hit Next
5. ✅ Upload cover page if you like, then hit Next
6. ⛔️ No need to publish as template, then hit "Publish to community"
7. ❇️ Copy the link and share with your friends