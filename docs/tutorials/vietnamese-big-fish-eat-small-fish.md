# Game: Cá Lớn Nuốt Cá Bé

### @explicitHints true


### ~button /#tutorial:/tutorials/chase-the-pizza

Try this tutorial!

### ~

## Introduction @showdialog

Mục đích của game này là bạn kiếm nhiều điểm nhất để ăn cá con.


## {Step 2}

**Đặt màu bối cảnh trò chơi**

---

- :tree: Mở <br/>
``||scene:Scene||``<br/>
từ toolbox, giữ và kéo <br/>
``||scene:set background color [ ]||`` <br/>
 đặt vào trong hộp trống ``||loops(noclick):on start||`` bên ngoài màn hình chính. 

~hint Nếu Bạn không biết làm thì nhấn vào đây 🤷🏽

---

Khi có hướng dẫn, đoạn code đã được bôi màu dễ nhìn để sử dụng vào viết chương trình

Ví dụ, khi chương trình gợi ý <br/>
``||scene:set background color to [ ]||``<br/>
bạn nên chỉ và nhấn chuột vào, thanh công cụ sẽ hiện lên cho bạn chọn sử dụng  <br/>

```block
scene.setBackgroundColor(13)
```

hint~

💡 _Hãy tuỳ chọn màu sắc mà bạn yêu thích_ 


---

- :mouse pointer: Nhấn **Next** để đi qua bước tiếp theo.


#### ~ tutorialhint
```blocks
// @highlight
scene.setBackgroundColor(13)
```


## {Step 3}

 Tạo nhân vật **sprite**.

---

- :paper plane: Mở ``||sprites:Sprites||`` giữ chuột và kéo <br/>
``||variables(sprites):set [mySprite] to sprite [ ] of kind [Player]||`` <br/>
 đặt dưới cuối của khối  ``||loops(noclick):on start||`` .

---


~hint sprite là gì nhỉ? 💡

---

 Trong chương trình, mỗi một nhân vật, đồ vật, hình ảnh ... đều được gọi là **SPRITE**.

-- Bạn có thể thay đổi hiện trạng của Sprites như thay đội vị trí, hình ảnh, tên, thời gian sống sót ...
.

Nhân vật chính của chúng ta cũng là sprite.

hint~


~hint Chỉ Tôi 🔍

![Add a sprite block](/static/tutorials/chase-the-pizza/mySprite.gif)

hint~


#### ~ tutorialhint
```blocks
let mySprite: Sprite = null
scene.setBackgroundColor(13)
// @highlight
mySprite = sprites.create(img`.`, SpriteKind.Player)
```

## {Step 4}
**Vẽ hình cho nhân vật chính**

- :mouse pointer: Vẽ hình cho sprite bằng cách di chuyển và bấm chuột vào ô vuông màu xám trên <br/> 
``||variables(sprites):set [mySprite] to sprite [ ] of kind [Player]||`` <br/>
 để mở **Sprite Editor**. <br/>
 Bạn có thể mở **Gallery** để chọn và chỉnh sửa hình ảnh của nhân vật.


- :mouse pointer: Nhấn **Done** sau khi bạn vẽ xong.

~hint Chỉ Tôi 🔍

![Image editor](/static/tutorials/chase-the-pizza/draw.gif)

hint~



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


## {Step 5}

**Làm nhân vật chính chuyển động theo sự điều khiển của mình**

---

- :game: Mở ``||controller:Controller||`` ấn chuột, kéo<br/> 
``||controller:move [mySprite] with buttons||``<br/>
và đặt xuống dưới dòng cuối cùng của khối<br/>
``||loops(noclick):on start||`` đã có sẵn.

Bây giờ thì bạn có thể di chuyển nhân vật của mình bằng nút lên xuống trái phải (hoặc là w s a d). 


~hint Chỉ Tôi 🔍

![Add the move block](/static/tutorials/chase-the-pizza/move.gif)

hint~


#### ~ tutorialhint
```blocks
let mySprite: Sprite = null
scene.setBackgroundColor(13)
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
// @highlight
controller.moveSprite(mySprite)
```




## {Step 6}

**Thử Trò chơi của mình trên máy**
- :binoculars:  Thử trò chơi của mình trên máy!

 Giờ bạn có thể di chuyển nhân vật của mình xung quanh màn hình.


![Look for the game window in the lower right](/static/tutorials/chase-the-pizza/game.png)







## {Step 7}

**Thêm cá nhỏ làm thức ăn**

---

- :paper plane: Mở ``||sprites:Sprites||``ấn giữ và kéo<br/> 
``||variables(sprites):set [pizza] to sprite [ ] of kind [Player]||``<br/> 
đặt xuống cuối của khối <br/>
``||loops(noclick):on start||``trên màn hình.


- :mouse pointer: Ấn **Player** in<br/>
``||variables(noclick):set [pizza] to sprite [ ] of kind [Player]||``<br/> và chọn  **Food**. Trong tiếng anh Food nghĩa là thức ăn.

---

~hint Chỉ Tôi 🔍

![Change the pizza to food](/static/tutorials/chase-the-pizza/food.gif)

hint~


```blockconfig.local
let pizza = sprites.create(img`.`, SpriteKind.Player)
```


#### ~ tutorialhint
```blocks
let mySprite: Sprite = null
let pizza: Sprite = null
scene.setBackgroundColor(13)
mySprite = sprites.create(img`
. . . . 5 5 5 5 5 5 5 . . . . . 
. . 5 5 5 5 5 5 5 5 5 5 5 . . . 
. 5 5 5 5 5 5 5 5 5 5 5 5 5 . . 
. 5 5 5 5 5 5 5 5 5 5 5 5 5 . . 
5 5 5 5 f 5 5 5 5 f 5 5 5 5 5 . 
5 5 5 5 f f 5 5 5 f f 5 5 5 5 . 
5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 . 
5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 . 
5 5 5 f f f f f f f f f 5 5 5 . 
5 5 5 5 f b b b b b f 5 5 5 5 . 
5 5 5 5 5 f b b b f 5 5 5 5 5 . 
. 5 5 5 5 5 f f f 5 5 5 5 5 . . 
. 5 5 5 5 5 5 5 5 5 5 5 5 5 . . 
. . 5 5 5 5 5 5 5 5 5 5 5 . . . 
. . . . 5 5 5 5 5 5 5 . . . . . 
. . . . . . . . . . . . . . . . 
`, SpriteKind.Player)
controller.moveSprite(mySprite)
// @highlight
pizza = sprites.create(img`.`, SpriteKind.Food)
```


## {Step 8}


- :mouse pointer: Choose your pizza by clicking the empty grey square inside <br/> 
``||variables(noclick):set [pizza] to sprite [ ] of kind [Food]||`` <br/>
to open the **Sprite Editor**. 

- :mouse pointer: Switch to the **Gallery** tab at the top. 
![Select the gallery](/static/skillmap/assets/gallery.png)


- :mouse pointer: Choose your pizza, then click **Done**.

~hint Show me 🔍

![Image gallery](/static/tutorials/chase-the-pizza/gallery.gif)

hint~


💡 _Feel free to draw your own pizza if you prefer!_

```blockconfig.local
let pizza = sprites.create(img`.`, SpriteKind.Player)
```


#### ~ tutorialhint
```blocks
let pizza: Sprite = null
let mySprite: Sprite = null
scene.setBackgroundColor(13)
mySprite = sprites.create(img`
. . . . 5 5 5 5 5 5 5 . . . . . 
. . 5 5 5 5 5 5 5 5 5 5 5 . . . 
. 5 5 5 5 5 5 5 5 5 5 5 5 5 . . 
. 5 5 5 5 5 5 5 5 5 5 5 5 5 . . 
5 5 5 5 f 5 5 5 5 f 5 5 5 5 5 . 
5 5 5 5 f f 5 5 5 f f 5 5 5 5 . 
5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 . 
5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 . 
5 5 5 f f f f f f f f f 5 5 5 . 
5 5 5 5 f b b b b b f 5 5 5 5 . 
5 5 5 5 5 f b b b f 5 5 5 5 5 . 
. 5 5 5 5 5 f f f 5 5 5 5 5 . . 
. 5 5 5 5 5 5 5 5 5 5 5 5 5 . . 
. . 5 5 5 5 5 5 5 5 5 5 5 . . . 
. . . . 5 5 5 5 5 5 5 . . . . . 
. . . . . . . . . . . . . . . . 
`, SpriteKind.Player)
controller.moveSprite(mySprite)
pizza = sprites.create(img`
. . . . . . b b b b . . . . . .
. . . . . . b 4 4 4 b . . . . .
. . . . . . b b 4 4 4 b . . . .
. . . . . b 4 b b b 4 4 b . . .
. . . . b d 5 5 5 4 b 4 4 b . .
. . . . b 3 2 3 5 5 4 e 4 4 b .
. . . b d 2 2 2 5 7 5 4 e 4 4 e
. . . b 5 3 2 3 5 5 5 5 e e e e
. . b d 7 5 5 5 3 2 3 5 5 e e e
. . b 5 5 5 5 5 2 2 2 5 5 d e e
. b 3 2 3 5 7 5 3 2 3 5 d d e 4
. b 2 2 2 5 5 5 5 5 5 d d e 4 .
b d 3 2 d 5 5 5 d d d 4 4 . . .
b 5 5 5 5 d d 4 4 4 4 . . . . .
4 d d d 4 4 4 . . . . . . . . .
4 4 4 4 . . . . . . . . . . . .
`, SpriteKind.Food)
```



## {Step 9}

**Make something happen when the sprites overlap!**

---

- :paper plane: Open ``||sprites:Sprites||`` and drag the<br/>
``||sprites:on [sprite] of kind [Player] overlaps [otherSprite] of kind [Food]||``<br/>
container into **an empty area** of the workspace.


🤷🏽‍♀️ _Need help? Click the lightbulb in the circle below to see what blocks you need in this step._



```blockconfig.local
let pizza = sprites.create(img`.`, SpriteKind.Player)
```


#### ~ tutorialhint
```blocks
// @highlight
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {

})
```



## {Step 10}

**Add a point when the sprites overlap**

---

- :id card: Open ``||info:Info||`` and drag<br/> 
``||info:change score by [1]||``<br/> 
into **the empty** <br/>
``||sprites(noclick):on [sprite] ... overlaps [otherSprite]||`` <br/>
container already in the workspace.


```blockconfig.local
let pizza = sprites.create(img`.`, SpriteKind.Player)
```

#### ~ tutorialhint
```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {
    // @highlight
	info.changeScoreBy(1)
})
```





## {Step 11}


- :binoculars: Check your game!

Notice that you get WAAAYYYYY too many points when your player 
sprite overlaps the pizza?  

We'll fix that in the next step.




## {Step 12}

**Teleport the pizza to a random location each time the sprites overlap.**

~hint What is random? 🤷🏽‍♀️

---

A "random" number is a value that you can't predict ahead of time. 

In Arcade, we use this block:

```block
randint(0, scene.screenWidth())
```

to ask for a random number between **0** and the **width of the screen**.

hint~

---

- :paper plane: Open ``||sprites:Sprites||``, and drag <br/>
``||sprites:set [pizza] position to...||``<br/> 
into the **end of the** <br/>
``||sprites(noclick):on [sprite] ... overlaps [otherSprite]||`` <br/>
container already in the workspace.


```blockconfig.local
let pizza = sprites.create(img`.`, SpriteKind.Player)
```

#### ~ tutorialhint
```blocks
let pizza: Sprite = null
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {
	info.changeScoreBy(1)
    // @highlight
    pizza.setPosition(randint(0, scene.screenWidth()), randint(0, scene.screenHeight()))
})
```




## {Step 13}

**Let’s start a countdown each time the sprites overlap.**

---

- :id card: From ``||info:Info||``, drag <br/>
``||info:start countdown [3] (s)||`` <br/> 
into the **end of the** <br/>
``||sprites(noclick):on [sprite] ... overlaps [otherSprite]||`` <br/>
container already in the workspace.


```blockconfig.local
let pizza = sprites.create(img`.`, SpriteKind.Player)
```

#### ~ tutorialhint
```blocks
let pizza: Sprite = null
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {
	info.changeScoreBy(1)
    pizza.setPosition(randint(0, scene.screenWidth()), randint(0, scene.screenHeight()))
    // @highlight
    info.startCountdown(3)
})
```


## {Finale}

**🎉 Great job! 🎉**

You've made a **Chase the Pizza** game.

Try playing your game. How many points can you get before time runs out?

When you're finished playing, click **Done** to share your game with family and friends!



```blockconfig.local
let pizza = sprites.create(img`.`, SpriteKind.Player)
```

#### ~ tutorialhint
```blocks
let pizza: Sprite = null
let mySprite: Sprite = null
scene.setBackgroundColor(13)
mySprite = sprites.create(img`
. . . . . 5 5 5 5 5 5 . . . . .
. . . 5 5 5 5 5 5 5 5 5 5 . . .
. . 5 5 5 5 5 5 5 5 5 5 5 5 . .
. 5 5 5 5 5 5 5 5 5 5 5 5 5 5 .
. 5 5 5 f f 5 5 5 5 f f 5 5 5 .
5 5 5 5 f f 5 5 5 5 f f 5 5 5 5
5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
5 5 f 5 5 5 5 5 5 5 5 5 5 f 5 5
5 5 5 f 5 5 5 5 5 5 5 5 f 5 5 5
. 5 5 5 f 5 5 5 5 5 5 f 5 5 5 .
. 5 5 5 5 f f f f f f 5 5 5 5 .
. . 5 5 5 5 5 5 5 5 5 5 5 5 . .
. . . 5 5 5 5 5 5 5 5 5 5 . . .
. . . . . 5 5 5 5 5 5 . . . . .
`, SpriteKind.Player)
controller.moveSprite(mySprite)
pizza = sprites.create(img`
. . . . . . b b b b . . . . . .
. . . . . . b 4 4 4 b . . . . .
. . . . . . b b 4 4 4 b . . . .
. . . . . b 4 b b b 4 4 b . . .
. . . . b d 5 5 5 4 b 4 4 b . .
. . . . b 3 2 3 5 5 4 e 4 4 b .
. . . b d 2 2 2 5 7 5 4 e 4 4 e
. . . b 5 3 2 3 5 5 5 5 e e e e
. . b d 7 5 5 5 3 2 3 5 5 e e e
. . b 5 5 5 5 5 2 2 2 5 5 d e e
. b 3 2 3 5 7 5 3 2 3 5 d d e 4
. b 2 2 2 5 5 5 5 5 5 d d e 4 .
b d 3 2 d 5 5 5 d d d 4 4 . . .
b 5 5 5 5 d d 4 4 4 4 . . . . .
4 d d d 4 4 4 . . . . . . . . .
4 4 4 4 . . . . . . . . . . . .
`, SpriteKind.Food)

sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {
	info.changeScoreBy(1)
    pizza.setPosition(randint(0, scene.screenWidth()), randint(0, scene.screenHeight()))
    info.startCountdown(3)
})
```


```blockconfig.global
let pizza: Sprite = null

scene.setBackgroundColor(13)
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {})
randint(0, scene.screenWidth())
pizza.setPosition(randint(0, scene.screenWidth()), randint(0, scene.screenHeight()))
info.startCountdown(3)

```

```package
chase-the-pizza=github:kiki-lee/chase-the-pizza
```