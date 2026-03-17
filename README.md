# Asteroids

An asteroids game made using Python's Pygame Library

## Overview

This is a classic Asteroids arcade game implementation in Python using Pygame. Navigate your spaceship through an asteroid field, destroying asteroids by shooting them while avoiding collisions. The game features collision detection, asteroid splitting mechanics, and event logging.

## Features

- **Player-controlled spaceship** - Navigate using keyboard controls
- **Asteroid spawning** - Asteroids spawn and move across the screen
- **Shooting mechanics** - Fire shots to destroy asteroids
- **Collision detection** - Detect collisions between the player and asteroids, and between shots and asteroids
- **Asteroid splitting** - When asteroids are hit, they split into smaller pieces
- **Game logging** - Events are logged to track gameplay (player hits, asteroid shots, game state)
- **60 FPS gameplay** - Smooth 60 frames per second game loop

## Project Structure

```
asteroids/
├── main.py              # Main game loop and entry point
├── player.py            # Player spaceship class
├── asteroid.py          # Asteroid class
├── asteroidfield.py     # Asteroid field/spawner class
├── shot.py              # Shot/bullet class
├── circleshape.py       # Circle collision shape base class
├── constants.py         # Game constants (screen dimensions, etc.)
├── logger.py            # Event and state logging
├── game_events.jsonl    # Game event log
├── pyproject.toml       # Project configuration
└── uv.lock              # Dependency lock file
```

## Requirements

- Python >= 3.14
- pygame == 2.6.1

## Installation

### Using uv (recommended)

If you have `uv` installed:

```bash
cd asteroids
uv sync
```

### Using pip

```bash
pip install pygame==2.6.1
```

## Running the Game

```bash
python asteroids/main.py
```

## How to Play

- **Arrow Keys** - Rotate and move your spaceship
- **Spacebar** - Fire shots at asteroids
- **Escape/Close Window** - Quit the game

**Objective:** Destroy all asteroids without colliding with them. When you shoot an asteroid, it splits into smaller pieces. Destroy all asteroids to progress.

## Game Mechanics

### Player
The player controls a spaceship in the center of the screen. The ship can rotate and move forward, and fire shots in the direction it's facing.

### Asteroids
Asteroids spawn around the screen and move in random directions. When hit by a shot, they split into smaller asteroids. When the player collides with an asteroid, the game is over.

### Collision Detection
The game uses circular collision detection to determine:
- When a shot hits an asteroid
- When the player collides with an asteroid

### Event Logging
The game logs events to `game_events.jsonl`:
- `player_hit` - When the player collides with an asteroid
- `asteroid_shot` - When a shot hits an asteroid
- Game state updates for debugging and analysis

## Development

The game uses object-oriented design with sprite-based classes for game entities:
- `Player` - Player-controlled spaceship
- `Asteroid` - Destructible asteroids
- `Shot` - Player projectiles
- `AsteroidField` - Manages asteroid spawning

All drawable objects inherit from or use `CircleShape` for collision detection.

## License

This project is open source. Feel free to use and modify as needed.
