# Chase the Pizza
### @explicitHints true


### ~button /#tutorial:/tutorials/chase-the-pizza

Try this tutorial!

### ~

## Introduction @showdialog

![Game animation](/static/tutorials/chase-the-pizza/chasing.gif)

Create a game where the goal is to eat as much pizza as you can 
before the time runs out! 


## {Step 1}

**Set the background color**

---

- :tree: Open the <br/><br/>
``||scene:Scene||``<br/>
toolbox drawer and drag <br/>
``||scene:set background color [ ]||`` <br/>
into **the empty** ``||loops(noclick):on start||`` container already in your workspace. 

~hint What does that mean? 🤷🏽

---

When giving instructions, we'll highlight some text to give you a better idea of what you are looking for.

For example, when we suggest the <br/>
``||scene:set background color to [ ]||``<br/>
block, we are pointing you toward <br/>

```block
scene.setBackgroundColor(13)
```

hint~

💡 _Feel free to choose your own color if you don't like the swatch in the block._ 


---

- :mouse pointer: Click the button that says **Next** to go to the 
next step of the tutorial.


#### ~ tutorialhint
```blocks
// @highlight
scene.setBackgroundColor(13)
```


## {Step 2}

Add a player **sprite**.

---

- :paper plane: Open the ``||sprites:Sprites||`` drawer and drag <br/>
``||variables(sprites):set [mySprite] to sprite [ ] of kind [Player]||`` <br/>
into **the end of** the  ``||loops(noclick):on start||`` block already in your workspace.

---


~hint What's a sprite? 💡

---

In Arcade, each character or image that does something is called a **SPRITE**.

Sprites have properties that you can use and change — 
things like scale, position, and lifespan are all properties of sprites.

Our player will be a sprite, too.

hint~


~hint Show me 🔍

![Add a sprite block](/static/tutorials/chase-the-pizza/mySprite.gif)

hint~


#### ~ tutorialhint
```blocks
let mySprite: Sprite = null
scene.setBackgroundColor(13)
// @highlight
mySprite = sprites.create(img`.`, SpriteKind.Player)
```

## {Step 3}

- :mouse pointer: Draw your sprite by clicking on the empty grey square in the <br/> 
``||variables(sprites):set [mySprite] to sprite [ ] of kind [Player]||`` <br/>
block to open the **Sprite Editor**. 


- :mouse pointer: Click **Done** when you are finished drawing.

~hint Show me 🔍

![Image editor](/static/tutorials/chase-the-pizza/draw.gif)

hint~
duy anh cu chuoi



#### ~ tutorialhint
```blocks
let mySprite: Sprite = null
scene.setBackgroundColor(13)
// @highlight
mySprite = sprites.create(img`
. . . . . 5 5 5 5 5 5 5 . . . . 
. . . 5 5 5 5 5 5 5 5 5 5 5 . . 
. . 5 5 5 5 5 5 5 5 5 5 5 5 5 . 
. . 5 5 5 5 5 5 5 5 5 5 5 5 5 . 
. 5 5 5 5 f 5 5 5 5 f 5 5 5 5 5 
. 5 5 5 5 f f 5 5 5 f f 5 5 5 5 
. 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 
. 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 
. 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 
. 5 5 5 f f f f f f f f f 5 5 5 
. 5 5 5 5 f b b b b b f 5 5 5 5 
. . 5 5 5 5 f b b b f 5 5 5 5 . 
. . 5 5 5 5 5 f f f 5 5 5 5 5 . 
. . . 5 5 5 5 5 5 5 5 5 5 5 . . 
. . . . . 5 5 5 5 5 5 5 . . . . 
. . . . . . . . . . . . . . . . 
`, SpriteKind.Player)
```


