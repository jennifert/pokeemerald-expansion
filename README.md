# Pokémon Verdant

**Pokémon Verdant** is the working codename for a work-in-progress Pokémon Emerald enhancement project built with [`pokeemerald-expansion`](https://github.com/rh-hideout/pokeemerald-expansion/).

The goal is to keep the heart of Hoenn intact while adding modern quality-of-life features, easier team building, one-save Hoenn Pokédex completion, and a warmer postgame full of useful rewards and playful surprises.

> **Status:** early development / testing build  
> **More features coming soon.**

## About This Project

Pokémon Verdant is designed as an enhanced Hoenn experience rather than a full replacement of Emerald. The main focus is:

- Making every Hoenn Regional Dex Pokémon obtainable in one save.
- Reducing unnecessary grinding and trade requirements.
- Adding modern conveniences from later Pokémon games.
- Keeping optional challenge settings separate from casual quality-of-life features.
- Building a strong Hoenn-focused base before larger future experiments.

No ROMs are included in this repository.

## Current Test Features

These features are currently planned for testing or already enabled in the development branch.

### Hoenn Dex Availability

- All Hoenn Regional Dex Pokémon should be obtainable in-game.
- Missing or version-exclusive lines are being moved into normal gameplay where appropriate.
- Surskit and Meditite are available in Hoenn.
- Lunatone and other version-exclusive Pokémon are available in one save.
- Feebas can be fished on Route 119.
- Trade evolutions are being replaced or supplemented with in-game evolution methods.

### Experience and Progression

- Gen 6-style Exp Share behavior.
- Reusable TMs.
- Bag-use evolution items, similar to Pokémon Legends: Arceus.
- Pokémon can learn moves from their pre-evolutions.

### Lilycove Department Store Updates

- Mail has been removed from the Lilycove Department Store.
- TMs have been moved to a dedicated clerk.
- Nature Mints have been added to another clerk.
- Ability Patch, Ability Capsule, and Link Cable are temporarily available on Floor 4 for testing.

### Item and Overworld Quality of Life

- First-time item description popups are enabled.
- ORAS-style Dowsing Machine support is enabled.
- Immortal berries are enabled.
- Berry mutations are enabled.
- TMs are reusable.

### Summary Screen and Pokémon Data

- EC information is visible.
- IV information is visible.
- Additional summary-screen information is being tested.

## Planned Features

These features are planned or being considered for later development.

### Friendship and Partner Features

- Start menu care option for checking friendship, petting Pokémon, and feeding berries.
- Friendship checker NPC improvements.
- Mom's Care system, where Mom can give party-wide affection based on badges earned or Elite Four clears.
- Following Pokémon support using `OW_FOLLOWERS_ENABLED`.
- Partner reactions for important story locations and cozy home moments.

### Team Building and Postgame Tools

- Ability Capsule and Ability Patch moved to final balanced locations.
- Nature Mints placed in a proper late-game or postgame shop.
- Exp Candies as postgame team-building tools.
- Buyable or improved access to key competitive items.
- Hidden Power type changer.
- Poké Ball changing service.
- Improved Move Relearner and Egg Move access.

### Hoenn Postgame Expansion

- Unchosen starter eggs after becoming Champion.
- Jirachi event at Mossdeep Space Center.
- AuroraTicket / Birth Island Deoxys access.
- Old Sea Map / Faraway Island Mew access.
- Optional bonus islands and legendary events.
- Improved rematches and postgame trainer challenges.

### Battle and Type Updates

- Fairy type support.
- Official-style Fairy retcons for existing Pokémon such as Mawile, Azumarill, Gardevoir, Clefairy, and others.
- Fairy move distribution.
- More modern held items.
- Optional improved boss teams.
- Optional challenge and assist settings.

### Interface and Future Features

- ORAS-style Key Item Wheel.
- Additional Start menu options.
- Improved Pokédex information.
- More quality-of-life settings.
- Multi-region support may be explored after the Hoenn-focused version is complete.

## Testing Checklist

Before considering a build stable, the following should be tested:

- Hoenn Regional Dex completion in one save.
- Updated wild encounters.
- Feebas fishing on Route 119.
- Exp Share behavior.
- Lilycove Department Store inventories.
- Reusable TMs.
- Nature Mints.
- Ability Patch, Ability Capsule, and Link Cable test placements.
- Immortal berry behavior.
- Berry mutations.
- First-time item description popups.
- Pre-evolution move learning.
- Summary screen EC and IV display.
- Bag-use evolution items.
- ORAS Dowsing Machine behavior.

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
