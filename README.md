# Hide in Plane Sight

A 2D Horror Platformer with Stealth and Arena Combat Elements  
Built in Unity 2D | By [Faisal18Ansari](https://github.com/Faisal18Ansari)

---

## Game Overview

**Hide in Plane Sight** is a single-level MVP (Minimum Viable Product) horror platformer that blends shadow-based stealth with sudden arena-style combat. You explore a dark, atmospheric world patrolled by terrifying sky monsters. Stay hidden, avoid detection, and survive lockdown combat phases to reach the exit.

---

## Core Game Loop

1. **Exploration Phase:** Move through the level, hiding behind objects to avoid monster light.
2. **Detection Event:** If caught in a monster’s light cone, you have a brief chance to escape.
3. **Combat Lockdown:** Detection triggers a lockdown; defeat spawned ground enemies to escape.
4. **Victory/Death:** Survive the arena or lose a life. Respawn and try again.
5. **Continue Exploration:** Continue toward the level exit.

This cycle creates tension and release, making every hiding spot precious and every mistake costly.

---

## Key Game Mechanics

### 1. Sky Monster Patrol System

- Two monsters patrol above the level, moving horizontally with unpredictable pauses and speed.
- Each emits a cone-shaped light (60° angle, 10-unit range).
- Detection occurs if the player is in the cone and not hidden by an object.
- If detected, the monster locks on and triggers a lockdown event.

### 2. Line-of-Sight Hiding

- Monsters cast rays to check if the player is visible.
- Environment objects block these rays; if blocked, the player is hidden.
- Intuitive “if you can’t see the monster, it can’t see you” logic.
- Visual feedback indicates when you’re hidden.

### 3. Combat Lockdown

- Detection triggers arena lockdown: invisible barriers spawn, trapping the player.
- 5–6 ground enemies spawn in a circle and must be defeated.
- After victory, barriers drop and the player gets brief immunity.

### 4. Health/Lives System

- The player has 3 lives; each hit costs a life, no health bar.
- Respawn at last checkpoint on death; lockdown resets.

### 5. Level Progression

- Reach the exit portal to complete the level.
- Exit activates only on approach.

---

## Technical Architecture

### Unity Layer Usage

- **Player:** Layer 8
- **Ground:** Layer 9
- **SkyMonsters:** Layer 10
- **GroundEnemies:** Layer 11
- **Environment:** Layer 12
- **Shadows:** Layer 13
- **LightCones:** Layer 14
- **Barriers:** Layer 15
- **UI:** Layer 16

**Collision Matrix:**  
- Player interacts with Ground, Environment, GroundEnemies, Barriers.  
- Shadows & LightCones trigger with Player only.  
- SkyMonsters float, no collisions.

### Folder Structure

```
Assets/
├── _Project/
│   ├── Scripts/
│   │   ├── Player/
│   │   ├── Enemies/
│   │   ├── Systems/
│   │   ├── UI/
│   │   └── Utilities/
│   ├── Prefabs/
│   ├── Sprites/
│   ├── Materials/
│   ├── Audio/
│   ├── Scenes/
│   └── Settings/
```

---

## Quick Start Guide

1. **Clone the repository** and open in Unity 2D (recommended 2021.3+).
2. **Set up layers** and physics matrix as described above.
3. **Open `Scenes/Level01.unity`** for the MVP level.
4. **Run the scene** and play!

---
## License

MIT License (see `LICENSE` file)
