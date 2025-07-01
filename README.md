# 🥷 Ninja Platformer Game

A fast-paced 2D ninja platformer built with **Pygame**, featuring dynamic movement mechanics, enemies, parallax clouds, particles, dashing, wall sliding, and a custom tile-based level editor.

![Ninja Game](Ninja_Game.gif)

---

## 🚀 Features

- ⚔️ Smooth ninja movement (run, jump, wall-slide, dash)
- 👾 Enemy AI with projectile attacks
- 🌄 Parallax cloud rendering for depth
- 🌿 Procedural leaf particles and spark effects
- 🧱 Tile-based level design with autotiling support
- 🛠️ Fully functional **custom level editor**
- 🎵 Background music and SFX (jump, dash, hit, shoot)
- 💥 Screenshake, particle explosions, and respawn logic
- 📦 Exported as `.exe` with **PyInstaller**

---

## 📂 Project Structure

```

ninja_game/
├── data/
│   ├── images/                             # Game sprites and tiles
│   │   ├── clouds/
│   │   ├── entities/
│   │   │   ├── enemy/
│   │   │   │   ├── idle/
│   │   │   │   └── run/
│   │   │   └── player/
│   │   │       ├── idle/
│   │   │       ├── jump/
│   │   │       ├── run/
│   │   │       ├── slide/
│   │   │       ├── wall_slide/
│   │   │       └── player.png
│   │   ├── particles/
│   │   │   ├── leaf/
│   │   │   └── particle/
│   │   └── tiles/
│   │       ├── decor/
│   │       ├── grass/
│   │       ├── large_decor/
│   │       ├── spawners/
│   │       ├── stone/
│   │       ├── background.png
│   │       ├── gun.png
│   │       └── projectile.png
│   ├── maps/                               # JSON level files
│   ├── sfx/                                # Sound effects
│   └── music.wav                           # Background music 
├── scripts/
│   ├── clouds.py                           # Cloud parallax background system
│   ├── entities.py                         # Player and enemy entities (PhysicsEntity) 
│   ├── particle.py                         # Leaf and impact particle system 
│   ├── spark.py                            # Fast spark particles 
│   ├── tilemap.py                          # Tilemap handling, rendering, saving
│   └── utils.py                            # Asset loader, animation class
├── editor.py                               # Tilemap level editor
├── game.py                                 # Main game loop
└── map.json

```

---

## 🕹️ Controls

**In Game (`game.py`):**

- `← →` – Move left/right  
- `↑` – Jump / Wall-jump  
- `X` – Dash  
- Gamepad support can be added manually

**In Editor (`editor.py`):**

- `W A S D` – Scroll the view
- Mouse Wheel – Cycle through tile groups
- **Shift + Wheel** – Cycle tile variants
- `G` – Toggle on-grid / off-grid placement
- `T` – Autotile terrain
- `O` – Save map to `map.json`

---

## ⚠️ Important Notes

### 🎮 Level Design Constraints

> To prevent game crashes and ensure a smooth experience when using the level editor:

- ✅ **Decor**, **enemy spawners**, and **special objects** must be placed in **off-grid mode**.  
  Placing them on the tile grid may break entity logic or cause the game to crash.

- ✅ The **player’s spawn point** (spawner with `variant: 0`) **must also be placed off-grid**.  
  This ensures the player correctly respawns at the beginning of the level after dying.  
  If omitted or mispositioned, the player may respawn where they were last hit instead.

---

## 🧪 Installation

1. **Clone the repository:**

   ```bash
   git clone https://github.com/yourusername/ninja-platformer.git
   cd ninja-platformer
    ```

2. **Install dependencies:**
    ```bash
    pip install pygame
    ```

3. **Run the game:**

    ```bash
    python game.py
    ```

4. _(Optional)_ Run the editor:

    ```bash
    python editor.py
    ```


---

## 🛠️ Build an Executable

To package the game into a `.exe` (Windows):

```bash
py -m PyInstaller game.py --noconsole
```

Make sure all asset folders (`data/images`, `data/maps`, `data/sfx`, etc.) are included alongside the `.exe`.

---

## 📜 License

MIT License

---

## 💡 Credits

- Developed using **Python** and **Pygame**    

---

## 🤝 Contributing

Feel free to fork this repo, submit issues, or open pull requests. Contributions are welcome!

---
