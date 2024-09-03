# Simple_Platformer

> `2024-08-20 5:00` using [Defold v1.9.1](https://defold.com/)

---

## 1. Спрайты, Тайлмапы, Базовая настройка

- [x] [Video_tutorial](https://www.youtube.com/watch?v=_EaoMUae-eg)
- [x] `/main/main.collection` -> наполнение сцены для рендеринга
![Outline/Collection](https://github.com/user-attachments/assets/fdc39feb-c0ea-471a-9295-41993b573cd6)

- Setting up project
- Adding basic visual assets (thanks to Kenney!)
- Making atlas with images
- Making tilesource
- Creating level scene with tilemaps
- Adding sprite representing our hero
- Running game

### In progress

![prgrss](https://github.com/user-attachments/assets/8daacdd9-20b3-4255-95fa-8cebcff4b30b)
  
### Result

![rslt](https://github.com/user-attachments/assets/3d778d6f-7c28-4a34-89da-5d23e9b8d186)

---

## 2 Ввод, Скрипт, Движение

> [Video_tutorial 2](https://www.youtube.com/watch?v=kO8m2xvx3sU)

```lua
function on_input(self, action_id, action)
    local position = go.get_position() -- get actual position of the current GameObj
    ...
end
```

- [`msg.post`](https://defold.com/ref/stable/msg/)
- [`API go.get_position`](https://defold.com/ref/stable/go/#go.get_position:[id])

### Steps

- Setting up input bindings
- Writing script for handling inputs
- Adding functionality to move game object according to inputs
- Adding functionality to play animations and flip sprites according to direction
- Attaching script to game object as component

---

## 3 Гравитация, Скорость, Столкновения

### Removed from on_input(self, action_id, action)

```lua
-- https://defold.com/ref/stable/msg/
-- https://defold.com/ref/stable/go/#go.get_position:[id]
```

### Functions

- [x] `walk()`
- [x] `flip()`

рефакторинг `on_input`:

- [x] замена конструкции `if_eleif` > тернарное выражение `local direction = (action_id == hash("right")) and DIRECTION_RIGHT or DIRECTION_LEFT`
и теперь мы направление движения присваиваем локальной переменной `direction` и передаём в

- `walk(direction)`
- `flip(direction)`

> утром сегодня пробовал(но герой постоянно двигался влево)

### Cravity

> `6:25 - timeCode`

1. Разделим перемещение персонажа на цикл обновления `fixed_update()`
2. ...[8:37]

### Hot Keys

| Move |Rotate | Scale |
|:-:|:-:|:-:|
|`W` |  `E` | `R`|

## Результат

- [x] Добавление реализации движения на основе гравитации и скорости
- [x] Добавление объектов столкновения к уровню и персонажу героя
- [x] Добавление форм столкновений на основе примитивной формы и источника плиток
- [x] Добавление обработки столкновений между героем и уровнем

## 4 Прыжки, отладка

> [YT_video](https://www.youtube.com/watch?v=53ptmzWFHZI)

- [x] проверить инпут-биндинг кнопки пробел(jump)
- [x] `[5:13]` |  `game.project` > Physics > `Use Fixed Timestep` == **ON!**
- в дебаг-режиме видно, что если герой запрыгнул на ящик, то при движении влево/вправо он не будет падать(продолжает левитацию -стоит на невидимом полу-)
