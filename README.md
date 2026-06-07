# 🐍 3D Snake Game
An immersive, retro-inspired **3D Snake Game** built using **Python** and **OpenGL (PyOpenGL)**. The game takes the classic 2D arcade formula and translates it into a dynamic 3D environment complete with camera rotation, multiple difficulty levels, obstacle generation, bombs, and an intense **First-Person View Mode**!
## ✨ Features
 * **Dual View Modes:**
   * **Third-Person Mode:** Rotate, tilt, and zoom your camera to inspect the entire grid.
   * **First-Person Mode:** Hit V to dive into the snake's eyes! Includes custom cockpit crosshairs and a **proactive proximity warning system** when obstacles or bombs are directly ahead.
 * **Procedural Map Generation:** Obstacles generate dynamically based on your chosen difficulty and scale as your score goes up.
 * **Dangerous Entities (Bombs):** Randomized bomb threats spawn and despawn intermittently, creating temporary no-go zones on the board.
 * **Special Power-ups:** Collect rare blue stars for temporary **Double Points** and an accompanying speed boost.
 * **Adaptive Environment:** Fun retro color-changing background triggers as you reach milestone point tiers.
## 🎮 Controls
### Game Management & UI
 * **Mouse Click**: Interact with UI buttons (Select difficulty, Start, Pause/Play).
 * **Spacebar / P**: Pause or Resume the match.
 * **R**: Reset and restart the game instantly.
 * **V**: Toggle between **Third-Person** and **First-Person** perspective.
 * **ESC**: Exit game.
### Snake Navigation
 * **Third-Person Mode:** Use Arrow Keys. Controls align directly to your nearest 90-degree locked board rotation angles (0^\circ, 90^\circ, 180^\circ, 270^\circ).
 * **First-Person Mode:** Use Left / Right Arrow Keys to make realistic 90-degree point-of-view turns, or Down Arrow to execute a quick reversal.
### Camera Movement (Third-Person Only)
 * **A / D**: Rotate the camera platform left or right.
 * **W / S**: Adjust the camera altitude up or down.
 * **X / Y**: Zoom the camera viewport in or out.
## 🛠️ Installation & Setup
### Prerequisites
Make sure you have Python 3.x installed along with the required libraries. You will need PyOpenGL and standard mathematical/time utility libraries.
### Step 1: Install Dependencies
You can install PyOpenGL via pip:
```bash
pip install PyOpenGL PyOpenGL_accelerate

```
*(Note: Windows users may occasionally require pre-compiled wheels for PyOpenGL if standard pip installations encounter driver path conflicts).*
### Step 2: Clone & Run
Clone this repository to your local directory and run the application script directly:
```bash
python 423_project.py

```
## 🧱 Game Mechanics & Architecture
### Difficulty Levels
The game supports three unique difficulty scales chosen directly from the interactive start screen menu:
| Difficulty Level | Base Snake Speed | Max Active Bombs | Obstacle Intensity |
|---|---|---|---|
| **Easy** | Slow | 1 Bomb Max | Minimal Groups |
| **Medium** | Moderate | 2 Bombs Max | Medium Cluster |
| **Hard** | Fast | 3 Bombs Max | Heavy Density |
### State Management
The project structures its workflow into a clean framework handling distinct engine rendering pipelines based on state changes:
 * START: Displays a comprehensive tutorial text dashboard layout alongside difficulty choice buttons.
 * PLAYING: Actively triggers time updates, entity movement logic calculations, physics evaluation updates, and object collisions.
 * PAUSED: Suspends updating element timelines (including double point counters and bomb lifespans) until execution resumes.
 * GAME_OVER: Renders your final score metric screen overlay with an instant option to drop back to menu initialization pools.
