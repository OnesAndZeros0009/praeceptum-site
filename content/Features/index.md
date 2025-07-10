---
title: "Features"
date: 2025-07-09
draft: false
---

# Praeceptum — Key Features

Praeceptum is packed with unique systems that make it unlike any other magic game. Here’s what makes it special:

---

## 🪄 Spell Casting

One of the core mechanics of Praeceptum is casting spells. Players can cast any spell at any time, provided their wand can handle it. A quick-access hotbar allows for fast casting of pre-assembled spells, but full mastery comes from crafting spells on the fly.

### Procedural Spell Language

Spells are made from syllables and words that are procedurally generated at the start of each run. Each syllable has its own meaning:

- `igni` → fire  
- `lux` → light  
- `ignilux` → fire + light spell

These syllables are combined into meaningful incantations. Spells with poorly combined or unpronounceable syllables may backfire, causing unexpected or harmful effects. The system rewards linguistic creativity, experimentation, and memory.

---

## ⚗️ Alchemy System

Praeceptum simulates a rich, interactive world of matter and magic. Inspired by falling-sand simulations, its alchemy engine is more advanced and more physically grounded.

### Multi-Material Tiles

Each tile in the world can contain a **mixture** of materials, not just a single type. For example:

- `Tile (8,5)` → 75% water, 15% dirt  
- `Tile (2,7)` → 92% air, 8% toxic gas

Tiles also track other properties like temperature, mass, and electric charge. These mixtures are processed as real chemical systems.

### Tags and Visualization

When displaying the content of a tile, the engine uses a dictionary of combinations to generate readable tags:

- `{75% water, 15% dirt}` → displays as “mud”

This tag system helps players recognize complex materials and their states quickly and intuitively.

### Reactions and Energy

Two materials occupying the same tile may react based on defined rules. Reactions may:

- Require a specific **activation temperature**
- Produce heat or consume it
- Generate new materials (e.g. dirt + acid → toxic sludge)

Heat is visualized using **black-body radiation coloring** added to a tile’s base color, allowing players to visually sense temperature. A tile’s final color is an average of its component materials and temperature effects.

---

## 🌡️ World Simulation

Praeceptum models the physical world in a detailed and rule-based way. Here’s how substances behave:

- **Diffusion**: All materials move into adjacent tiles that aren’t full.
- **Buoyancy**: Liquids and gases rise or sink based on their density and temperature.
- **Gravity**: Most materials prefer to move downward, influenced by mass and state.
- **Independent Properties**: Heat, electric charge, and other values also diffuse—but are not affected by gravity or buoyancy.

Each substance affects the tile it’s in. For example:

```c++
iron {
  electricalConductivity = 0.9f
  thermalConductivity = 0.7f
}
