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
