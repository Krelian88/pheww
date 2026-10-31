# Pheww!

A top-down arena shooter with roguelite progression, made in Godot 4.7.2.

You play Jocky Rogers, the technical officer of a ship that crashed on the
alien planet Verath-5. You start with a scavenged handgun and not much else.
Every death sends you back to the med-pod, where you spend what you collected
on upgrades and try again.

## Status

Early development. The current build is the original arcade prototype: one
level with four segments and a boss. The vertical slice (two levels, skill
tree, workbench, save slots) is in progress.

## Requirements

- Godot 4.7.2, standard build (GDScript)
- Windows 10 or 11
- Git. GitHub Desktop works fine.

## Open and run

1. Clone this repository.
2. Open Godot, click Import, and select `project.godot`.
3. Wait for the first import to finish.
4. Press F5 to run.

## Controls

| Action        | Keyboard and mouse  |
| ------------- | ------------------- |
| Move          | WASD or arrow keys  |
| Aim           | Mouse               |
| Fire          | Left click or Space |
| Throw grenade | Q or right click    |
| Pause         | Esc                 |

## Project layout

Folders are snake_case and grouped by feature: each scene sits next to its
script, art and data. Files several features share live in `audio/` and
`fonts/`.

| Folder       | Contents                                              |
| ------------ | ----------------------------------------------------- |
| `audio/`     | Music (`music/`) and sound effects (`sfx/`)           |
| `autoloads/` | Global singletons, such as `game_data.gd`             |
| `enemies/`   | `enemy_base.gd`, one folder per enemy, and the boss   |
| `fonts/`     | Fonts                                                 |
| `levels/`    | The game level, segment manager, backgrounds, props   |
| `pickups/`   | Power-ups and their sprites                           |
| `player/`    | The player, gun and attract-mode AI                   |
| `ui/`        | HUD art, menus and the CRT overlay                    |
| `weapons/`   | Bullets and grenades                                  |
| `_archive/`  | Unused assets kept for reference; Godot ignores it    |
| `addons/`    | Third-party plugins                                   |

## Plugins in use

- Aseprite Spritesheet Importer
- Dialogue Manager
- GDQuest GDScript Formatter
- Simple GUI Transitions
- Godot MCP and Claude Bridge (development tools only)

## Saves and settings

The game stores settings and save files in `%APPDATA%\Pheww` on Windows.

## Export

Export presets are not set up yet.

## License

Copyright (c) 2026 Adrian Lopez Adriano. All rights reserved.
