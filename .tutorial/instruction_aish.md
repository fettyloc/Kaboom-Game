# Kaboom platformer remix

## 1. Try the game first

- This is a simple 2 level mario-like platformer game. 
- Before changing any code, try running the game first! (Hit the "Run" button)
- Click on `console` and then `cmd +s` to start the game.
- Can you figure out how to play?

<details>
<summary>Hint💡</summary>
Use the space bar to jump and arrow keys to move
</details>

## 2. Look at the game map

- This is the game map. There are two `LEVELS` in this game that start and end with `[ ]`.
- Each character on the game map represents a sprite. For example, the `=` means grass.


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

<details><summary>Look at the code to see each sprite</summary>

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

## 3. Change some of the sprites
- Can you change some of the characters in the game map code below to make the level look different?
- Maybe you add more `$` (coins) or take away the `#` (apples). The choice is yours!

  
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

## 4. Run the changes
- Choose `run` and see what happens? Do you see your changes to the game appear? 

## Extra Credit
## 5. Add your own sprites

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

## 6. Add New Mechanics

### .onCollide(
Using 
```js
player.onCollide("sun", "earth", () => {
    addExplosion()
})
```
can you change `sun`, `earth` with another sprite the player could collide with to create an explosion? Maybe you add a new sprite?

## 7. Share your game!
### Don't be shy - the community loves it! 
1. ✅ Hit publish on top right, 
2. ✅ Give it a name, then hit Next
3. ✅ Add tags like #firstBuild #drawing, then hit Next
4. ✅ Upload an icon if you like, then hit Next
5. ✅ Upload cover page if you like, then hit Next
6. ⛔️ No need to publish as template, then hit "Publish to community"
7. ❇️ Copy the link and share with your friends

## Want to learn more about Kaboom?
- Kaboom.js is a Replit created JavScript library that helps you build games fast.
- To learn more about Kaboom check out another [snake game tutorial here](https://docs.replit.com/tutorials/build-snake-with-kaboom).
  - Note : Clicking the link will open a new tab. Try opening it in a new window and code side by side.