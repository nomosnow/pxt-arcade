# Game: Cá Lớn Nuốt Cá Bé

## {Step 1}

Here is some text.

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
duong veo cu chuoi



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


