# Contributing to Pheww!

These are the conventions for this project. They follow the official Godot
GDScript style guide and project organization guide, so anyone who knows
Godot should feel at home.

## Naming

| Element                    | Convention                        | Example                             |
| -------------------------- | --------------------------------- | ----------------------------------- |
| Files and folders          | snake_case                        | `enemy_base.gd`, `assets/art/`      |
| Node names                 | PascalCase                        | `SegmentManager`, `HealthComponent` |
| Classes                    | PascalCase                        | `class_name WeaponData`             |
| Functions and variables    | snake*case, `*` prefix if private | `take_damage()`, `_is_dead`         |
| Signals                    | snake_case, past tense            | `enemy_died`, `score_changed`       |
| Constants and enum members | CONSTANT_CASE                     | `MAX_SPEED`, `Type.RAPID_SHOT`      |
| Animation names            | snake_case                        | `idle`, `walk`, `run_up`, `die`     |

Some older files do not follow this yet. Fix them when you touch them, in a
commit of their own.

## Script layout

Keep this order inside every script:

1. `class_name`, then `extends`
2. Signals
3. Enums
4. Constants
5. `@export` variables
6. Other variables
7. `@onready` variables
8. `_ready()` and other built-in callbacks
9. Public methods
10. Private methods

Use static typing everywhere:

```gdscript
var health: int = 0

func take_damage(amount: int) -> void:
    health -= amount
```

## Structure

- Build entities from small component nodes (for example `HealthComponent`)
  instead of deep inheritance.
- Call down, signal up. A parent calls methods on its children. A child
  reports to its parent with signals and never reaches upward by node path.
- Keep tunable numbers in `Resource` files (`.tres`), not in scripts.
- Keep autoloads few. They hold global state only.
- Name physics layers and input actions in Project Settings. Do not use raw
  numbers in code.

## Assets

- Every visual uses an `AnimatedSprite2D`, even when it has one frame for now.
- Sprites are made in Aseprite and imported with the Aseprite importer.
- New audio nodes go on the `BGM` or `SFX` bus.
- Move or rename files only in Godot's FileSystem panel, never in File
  Explorer. Godot updates the references for you.

## Before you commit

1. Run the game (F5) and check the Output panel for new errors.
2. Run the GDScript formatter on the files you changed.
3. Keep one task per commit, with a message that says what changed.
