# Pokémon Verdant

**Pokémon Verdant** is the working codename for a work-in-progress Pokémon Emerald enhancement project built with [`pokeemerald-expansion`](https://github.com/rh-hideout/pokeemerald-expansion/).

The goal is to keep the heart of Hoenn intact while adding modern quality-of-life features, easier team building, one-save Hoenn Pokédex completion, and a warmer postgame full of useful rewards and playful surprises.

> **Status:** early development / testing build  
> **More features coming soon.**  
> For current implementation status, testing notes, and future planning, check the [GitHub issues](https://github.com/jennifert/pokeemerald-expansion/issues) and [milestones](https://github.com/jennifert/pokeemerald-expansion/milestones).
 
## About This Project

Pokémon Verdant is designed as an enhanced Hoenn experience rather than a full replacement of Emerald. The main focus is:

- Making every Hoenn Regional Dex Pokémon obtainable in one save.
- Reducing unnecessary grinding and trade requirements.
- Adding modern conveniences from later Pokémon games.
- Keeping optional challenge settings separate from casual quality-of-life features.
- Building a strong Hoenn-focused base before larger future experiments.

No ROMs are included in this repository.

> Pokémon Verdant is currently a personal hobby project and is not accepting outside contributions at this time. See `CONTRIBUTING.md` for details.

## Release Roadmap

Pokémon Verdant uses milestone-based versioning. Early versions are testing snapshots, while later `0.x` releases represent larger feature milestones. The goal is for `v1.0.0` to represent the complete main Pokémon Verdant release.

| Version | Milestone | Focus |
|---|---|---|
| `v0.0.1-test` | First Feature Test Pass | Early testing snapshot for encounter, item, Exp Share, summary screen, and quality-of-life changes. |
| `v0.1.0` | Early/Midgame Rewards & Economy | Item placement, daily rewards, early gifts, shop progression, and economy updates. |
| `v0.2.0` | QoL & Interface Pass | Interface improvements, expanded bag space, bike QoL, mute/low HP settings, and other comfort features. |
| `v0.3.0` | Battle Systems & Balance | Gym/E4 updates, battle item balance, move/item synergy, and trainer rebalance work. |
| `v0.4.0` | Postgame Events & Gifts | Postgame NPCs, legendary/event access, gift Pokémon, rematches, and extra rewards. |
| `v0.5.0` | DexNav / PokéNav Tools | Area checklists, PokéNav/DexNav utilities, Pokédex improvements, and navigation tools. |
| `v0.6.0` | Challenge & Assist Settings | Optional challenge rules, assist settings, accessibility/testing toggles, and related systems. |
| `v0.7.0` | Flavor & Visual Polish | Verdant flavor text, visual identity, title/load screen polish, and optional easter eggs. |
| `v1.0.0` | Complete Main Release | Main Pokémon Verdant roadmap complete and tested. |

Release notes will be tied to GitHub milestones when possible. Testing builds may be marked as pre-releases. Public releases should be distributed as patch files only, never as `.gba` ROM files.

Companion projects such as the documentation website and campaign/team builder may use their own milestones and do not necessarily affect the ROM version number.

## Feature Overview

This section describes the kinds of features Pokémon Verdant is planned to include. Not every feature listed here is implemented yet. For the most accurate current status, see the GitHub issues and milestones.

### Hoenn Dex and Availability

- All Hoenn Regional Dex Pokémon obtainable in one save.
- Version-exclusive and difficult-to-obtain Pokémon folded into normal gameplay.
- More reasonable access to rare Pokémon such as Feebas, Surskit, Meditite, Lunatone, and other availability pain points.
- Trade evolution alternatives through in-game items or services.

### Progression and Team Building

- Modern Exp Share behavior.
- Reusable TMs.
- Bag-use evolution items.
- More accessible move relearning, egg moves, and tutor moves.
- Better access to Nature Mints, Ability Capsule, Ability Patch, Hidden Power customization, and competitive held items.
- Postgame breeding support, including a special Ditto gift and Destiny Knot access.

### Quality of Life and Interface

- Following Pokémon support.
- Expanded bag space.
- Reusable Escape Rope Key Item.
- ORAS-style Dowsing Machine support.
- Optional mute and low-HP beep settings.
- Possible ORAS-style Key Item Wheel.
- Pokémon Center services such as box healing and Poké Ball changing.

### Rewards, Shops, and Economy

- Staged item shops that unlock useful items as the story progresses.
- Daily berry rewards from home.
- Early-game support items that help without removing challenge.
- Postgame shops for team-building and Battle Frontier preparation.

### Battle and Balance

- Verified Fairy type support from `pokeemerald-expansion`.
- Modern battle items and move/item synergy.
- Optional boss team updates for Gym Leaders and Elite Four.
- Later Battle Frontier improvements, including move tutors, a BP broker, and postgame utility NPCs.

### Challenge and Assist Options

- Challenge Settings for stricter rules such as level caps, held-only battle items, required nicknames, Nuzlocke tracking, and first-encounter rules.
- Assist Mode settings for comfort and testing, such as auto-heal, no wild encounters, EXP/money multipliers, one-hit capture, and shiny mode.
- Challenge features and assist features are planned to stay separate.

### Postgame and Flavor

- Postgame NPC battles and gifts.
- In-game access to event-style content such as Aurora Ticket / Birth Island.
- Bill, Mom, Birch, Nursery, and Battle Frontier postgame additions.
- Cozy partner reactions, optional flavor text, regional-form rumors, and small easter eggs.

### Companion Projects

Pokémon Verdant may also have companion projects, tracked separately from the ROM version:

- Documentation website.
- Team builder / campaign helper.
- Data references for Pokémon, moves, items, encounters, and team planning.

## Development Status

The README is intended to describe the project direction, not act as the source of truth for what is finished.

Use GitHub for the latest status:

- [Open issues](https://github.com/jennifert/pokeemerald-expansion/issues) track planned work, bugs, polish tasks, and research notes.
- [Milestones](https://github.com/jennifert/pokeemerald-expansion/milestones) group issues into release phases.
- Release notes will summarize what has actually been tested and included in each version.

## Build Instructions

This project is based on `pokeemerald-expansion`, so the original build process still applies.

See:

- [Installing pokeemerald-expansion](INSTALL.md)
- [Building pokeemerald-expansion](INSTALL.md#Building-pokeemerald-expansion)
- [Updating pokeemerald-expansion](INSTALL.md#Updating-pokeemerald-expansion)

Do not use GitHub's **Download ZIP** option if you plan to update, merge branches, or preserve project history.

## Credits

Pokémon Verdant is based on **RHH's `pokeemerald-expansion`**, which is built on top of [pret's `pokeemerald`](https://github.com/pret/pokeemerald) decompilation project.

Please credit **RHH (Rom Hacking Hideout)** and the `pokeemerald-expansion` contributors.

```text
Based off RHH's pokeemerald-expansion 1.16.1 https://github.com/rh-hideout/pokeemerald-expansion/
```

Additional credits should be added here as features, tutorials, assets, or external branches are incorporated.

Planned credit reminders:

- RHH / `pokeemerald-expansion`
- pret / `pokeemerald`
- ORAS-style Key Item Wheel author, if added
- Multi-region support contributors, if added
- Any sprite, music, tutorial, or feature contributors used later

## Disclaimer

This is a fan-made, non-commercial project. Pokémon is owned by Nintendo, Game Freak, and The Pokémon Company. No official ROM files are provided.
