# Game: Cá Lớn Nuốt Cá Bé

### @explicitHints true


### ~button /#tutorial:/tutorials/chase-the-pizza

Try this tutorial!

### ~

## Giới thiệu @showdialog

Mục đích của game này là ăn cá con để đạt được nhiều điểm nhất.


## {Step 2}

**Đặt màu bối cảnh trò chơi**

---

- :tree: Mở <br/>
``||scene:Scene||``<br/>
từ bộ công cụ (toolbox), giữ và kéo khối<br/>
``||scene:set background color [ ]||`` <br/>
 thả vào khe trống của hộp ``||loops(noclick):on start||`` bên ngoài màn hình chính. 

~hint Nếu bạn chưa hiểu cách làm, hãy nhấn vào đây 🤷🏽

---

Khi có hướng dẫn, có thể tương tác với các đoạn code (đã được bôi màu dễ nhìn hơn) để thuận tiện việc viết chương trình

Ví dụ, khi chương trình gợi ý <br/>
``||scene:set background color to [ ]||``<br/>
bạn chỉ cần đưa chuột vào cụm từ đó và nhấn chuột, thanh công cụ sẽ tự động hiện lên mục tương ứng để bạn chọn sử dụng  <br/>

```block
scene.setBackgroundColor(13)
```

hint~

💡 _Hãy thay đổi sang màu sắc mà bạn yêu thích bằng cách kích vào ô màu mặc định_ 


---

- :mouse pointer: Nhấn **Next** để sang bước tiếp theo.


#### ~ tutorialhint
```blocks
// @highlight
scene.setBackgroundColor(13)
```


## {Step 3}

 Tạo nhân vật **sprite**.

---

- :paper plane: Mở ``||sprites:Sprites||`` , giữ chuột và kéo <br/>
``||variables(sprites):set [mySprite] to sprite [ ] of kind [Player]||`` <br/>
 thả vào cuối của khối  ``||loops(noclick):on start||`` .

---


~hint sprite là gì nhỉ? 💡

---

 Trong chương trình, mỗi một nhân vật, đồ vật, đối tượng ... đều được gọi là **SPRITE**.

 Bạn có thể thay đổi hiện trạng của Sprites như: vị trí, hình ảnh, tên, thời gian sống sót ...

Nhân vật chính được điều khiển trong chương trình của chúng ta cũng thường là sprite.

hint~


~hint Hướng dẫn bằng hình ảnh 🔍

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
**Tạo hình cho nhân vật chính**

- :mouse pointer: Tạo hình cho nhân vật (sprite) bằng cách di chuyển và bấm chuột vào ô vuông màu xám trên <br/> 
``||variables(sprites):set [mySprite] to sprite [ ] of kind [Player]||`` <br/>
 để mở **Sprite Editor**. <br/>
 Bạn có thể mở **Gallery** để chọn và chỉnh sửa hình ảnh của nhân vật theo các mẫu có sẵn.


- :mouse pointer: Nhấn **Done** sau khi bạn hoàn thành.

~hint Hướng dẫn bằng hình ảnh 🔍

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

**Làm nhân vật chính di chuyển theo sự điều khiển của mình**

---

- :game: Mở ``||controller:Controller||`` giữ chuột, kéo<br/> 
``||controller:move [mySprite] with buttons||``<br/>
thả vào dòng cuối cùng của khối<br/>
``||loops(noclick):on start||`` đã có sẵn trên màn hình chính.

Giờ thì bạn có thể di chuyển nhân vật của mình bằng nút lên xuống trái phải (hoặc là w s a d). 


~hint Hướng dẫn bằng hình ảnh 🔍

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

**Thử trò chơi của mình trên máy**
- :binoculars:  Thử trò chơi của mình trên máy!
<br/>
 Giờ bạn có thể di chuyển nhân vật của mình xung quanh màn hình (sử dụng các phím mũi tên).


![Look for the game window in the lower right](/static/tutorials/chase-the-pizza/game.png)







## {Step 7}

**Thêm cá nhỏ làm thức ăn**

---

- :paper plane: Mở ``||sprites:Sprites||`` ấn giữ và kéo<br/> 
``||variables(sprites):set [ca_con] to sprite [ ] of kind [Player]||``<br/> 
thả vào cuối của khối <br/>
``||loops(noclick):on start||`` trên màn hình.


- :mouse pointer: Kích chuột vào **Player** trong khối<br/>
``||variables(noclick):set [ca_con] to sprite [ ] of kind [Player]||``<br/> và đổi thành  **Food**. (Trong tiếng anh Food nghĩa là thức ăn).

---

~hint Hướng dẫn bằng hình ảnh 🔍

![Change the pizza to food](/static/tutorials/chase-the-pizza/food.gif)

hint~


```blockconfig.local
let ca_con = sprites.create(img`.`, SpriteKind.Player)
```


#### ~ tutorialhint
```blocks
let mySprite: Sprite = null
let ca_con: Sprite = null
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
ca_con = sprites.create(img`.`, SpriteKind.Food)
```


## {Step 8}

**Tạo hình cho cá con**

---

- :mouse pointer: Thay đổi hình ảnh của mồi săn (cá con) bằng cách kích chuột vào ô màu xám trong khối <br/> 
``||variables(noclick):set [pizza] to sprite [ ] of kind [Food]||`` <br/>
để mở chức năng **Sprite Editor**. 

- :mouse pointer: Chọn mục **Gallery** phía trên nếu muốn dùng các mẫu có sẵn. 
![Select the gallery](/static/skillmap/assets/gallery.png)


- :mouse pointer: Kích chuột vào mẫu ưng ý, rồi ấn **Done**.

~hint Hướng dẫn bằng hình ảnh 🔍

![Image gallery](/static/tutorials/chase-the-pizza/gallery.gif)

hint~


💡 _Bạn có thể thoả sức sáng tạo cá con mình thích nếu không muốn sử dụng mẫu có sẵn nhé!_

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

**Thiết lập khi nhân vật chính ăn được mồi**

---

- :paper plane: Mở công cụ ``||sprites:Sprites||`` kéo khối<br/>
``||sprites:on [sprite] of kind [Player] overlaps [otherSprite] of kind [Food]||``<br/>
và thả vào **Khu vực trống bất kì** trên màn hình chính.


🤷🏽‍♀️ _Sử dụng gợi ý (hình bóng đèn phía dưới) nếu bạn không biết phải tìm đối tượng cần kéo thả._



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

**Tính điểm khi nhân vật chính ăn được mồi**

---

- :id card: Mở công cụ ``||info:Info||`` , kéo khối <br/> 
``||info:change score by [1]||``<br/> 
và thả vào **khe trống** của khối <br/>
``||sprites(noclick):on [sprite] ... overlaps [otherSprite]||`` <br/>
mà ta vừa đặt ở màn hình chính.


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


- :binoculars: **Kiểm tra chương trình của bạn!**

Bạn có thấy mỗi lần nhân vật chính chạm vào con mồi thì nó không ăn mồi? điểm số thì vẫn tăng lên liên tục, nhưng con mồi mới thì không xuất hiện thêm không? Điều này quả là không hợp lý nhỉ?   

Hãy cùng sửa nhé!




## {Step 12}

**Cho con mồi mới xuất hiện một các ngẫu nhiên**


~hint Ngẫu nhiên nghĩa là gì? 🤷🏽‍♀️

---

Giá trị **ngẫu nhiên** thể hiện việc nhân vật có thể xuất hiện ở bất cứ đâu trên màn hình. 

Trong các chương trình, ta sử dụng khối:

```block
randint(0, scene.screenWidth())
```

Và thiết lập giá trị biến đổi có thể có giá trị nhỏ nhất là **0** và lớn nhất có thể bằng độ lớn của  **màn hình hiển thị**.

hint~

---

- :paper plane: Trong công cụ ``||sprites:Sprites||`` ,kéo khối <br/>
``||sprites:set [sprite] position to...||``<br/> 
và thả vào **cuối khe trống** trong khối <br/>
``||sprites(noclick):on [sprite] ... overlaps [otherSprite]||`` <br/>
trên màn hình chính.


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

**Thiết lập thời gian tối đa cho một lần ăn mồi**

---

- :id card: Từ công cụ ``||info:Info||``, ta kéo khối <br/>
``||info:start countdown [3] (s)||`` <br/> 
và thả vào **cuối khe trống** trong khối <br/>
``||sprites(noclick):on [sprite] ... overlaps [otherSprite]||`` <br/>
trên màn hình chính.

Bạn có thể thay đổi thời gian tối đa cho 1 lần săn mồi bằng cách kích vào ô giá trị và thay đổi bằng giá trị bạn mong muốn.

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

**🎉 Tuyệt vời! 🎉**

Bạn đã hoàn thành chương trình **Cá lớn nuốt cá bé** .

Hãy kiểm tra thành quả của mình và thử xem kỷ lục điểm số có thể đạt được của bản thân là bao nhiêu nhé!

Ngoài ra, đừng ngại chia sẻ thành quả này với bạn bè và xem ai là người chơi giỏi nhất nhé!



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