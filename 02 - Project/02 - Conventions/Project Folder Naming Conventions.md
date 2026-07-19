```
Assets/
├── _Levels
├── _Project
├── _Scripts
└── _Tests
```

The leading underscore (`_`) in folder names is intentional. It keeps our core project folders grouped at the top of Unity's Project window (sorted alphabetically) and clearly separates them from third-party plugins, packages, SDKs, and add-ons added later.

Third-party content must remain in its own vendor/package folder and must not be moved into our `_` folders unless it becomes maintained project content.

---

## `_Levels`

Holds every Unity scene in the project. Do **not** create or use a folder named `_Scenes` — `_Levels` is deliberately chosen because it is easier to distinguish from `_Scripts` at a glance.

---

## `_Project`

All non-code, first-party game assets and project-owned content. Recommended subfolder structure:

```
_Project/
├── Art            # 2D sprites, textures, concept art, UI assets
├── Audio          # Sound effects, music, voice-over, audio mixers
├── Materials      # Unity materials
├── Models         # 3D models (FBX, glTF, etc.) and their imported assets
├── Textures       # Raw texture files and texture atlases
├── Animations     # Animation clips, controllers, avatars
├── Prefabs        # Reusable prefabs
├── UI             # UI-specific assets (panels, buttons, fonts, etc.)
├── VFX            # Visual effect assets (shuriken, VFX Graph, etc.)
├── Config         # ScriptableObject configs, game balance tables
├── Settings       # Project-level Unity Settings overrides (e.g. Input, Layer)
├── Fonts          # Font files (TTF, OTF)
└── Shaders        # Shader files and shader graphs
```

Subdivide further as the project grows (e.g. `Audio/Music`, `Audio/SFX`).

---

## `_Scripts`

All first-party C# code. Recommended subfolder structure:

```
_Scripts/
├── Core           # Singletons, entry points, dependency injection, base classes
├── Gameplay       # Player, enemies, items, mechanics, systems
├── UI             # UI controllers, HUD, menus, widgets
├── Utilities      # Extension methods, helpers, math, pooling
├── Editor         # Custom editor tools, inspectors, windows, asset postprocessors
└── Tests          # Play-mode and edit-mode unit tests
```

---

## `_Tests`

Prototypes, experiments, temporary imports, sandbox scenes, reproduction projects, and content not yet approved as real game content. **Nothing in `_Tests` may be referenced by production scenes or included in builds.** Treat this folder as a staging and experimentation space. We would remove this folder before a final build to make sure there is no dependency on it.
