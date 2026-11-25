# Pokémon Verdant
## Master project document
**Working reference • November 24, 2026**

### 1. Project identity and scope
Pokémon Verdant is a hobby enhancement of Pokémon Emerald, built on RH-Hideout's pokeemerald-expansion. The goal is a recognizable Hoenn adventure with modern conveniences, better access to team-building resources, a one-save Hoenn Pokédex, and a warmer, more rewarding postgame. It is a Gen III-based custom game with selectively enabled later-generation mechanics, not a Gen VI game. Development is undertaken alongside a full-time job; future features are possibilities, not release promises.

- ROM fork: https://github.com/jennifert/pokeemerald-expansion
- Upstream: https://github.com/rh-hideout/pokeemerald-expansion
- Companion site: `pokemon-verdant` (repository name from prior discussions; access not verified).
- Shared builder: https://github.com/jennifert/pokemon-builder-public
- Technologies: C, Make, GitHub, pokeemerald-expansion; Next.js was proposed for the companion site; SQLite for the shared builder overhaul.
- Separate projects (Soul Yellow, Soul Sage, Sage, Crystal Complete) are outside this document, except the possible shared artist commission.

**Status key:** Confirmed = explicitly recorded test/checklist result; Planned = discussed or open issue; Proposed = design candidate, not finalized; Closed = GitHub issue closure, not automatically an implementation claim. GitHub status reflects the retrieved snapshot. This document is a synthesis, not a complete transcript or code audit.

### 2. Foundations and verified progress
- #4 completed: Route 101 Zigzagoon moved into a higher-weight encounter slot; encounter testing completed.
- #5 completed: one Oran Berry in the player's starting PC, withdrawal and save/reload verified; first rival balance checked.
- #6 partially checked: Devon researcher gives Gen VI-style Exp. Share after the Petalburg Woods grunt; one-time flag, dialogue and bag pocket checked. Lucky Egg replaces the original Steven-letter reward; actual reward delivery, duplication protection and level curve still need testing.
- #3 partially checked: reusable TMs, Gen VI-style Exp. Share, immortal fully grown berries, first-acquisition item descriptions, 15 Poké Balls from Brendan/May, EV/IV summary displays, early Poké Mart, planting/growing/picking berries, and summary testing. Pending: berry mutations, pre-evolution moves, bag-use evolution items, ORAS Dowsing Machine, modern same-species Egg Move transfer, save/load and story regression.
- #1 partially checked: Surskit, Lotad line and Seedot line availability. Remaining species and evolution checks below.
- #2 remains open: Lilycove shop changes and item testing; temporary placements do not establish final unlocks.
- #56–64 remain open: planned breeding improvements under Milestone 12.

### 3. Pokédex, encounters and evolution
**Core goal:** Hoenn regional availability in a single save without link trading, version exclusives or external events. The original #1 excludes unchosen starters; #41 later proposes making both available. Hoenn completion uses caught flags; bonus non-Hoenn Pokémon and Deoxys should not be required. Reconcile the original 202-entry reference dataset with the chosen completion policy.

- Verify Surskit/Masquerain, Meditite/Medicham, Lunatone/Solrock, Lotad and Seedot lines, Sableye/Mawile, Zangoose/Seviper, Volbeat/Illumise, Feebas/Milotic. Verify Pokédex area data, rates and intended postgame gates.
- Make Feebas reasonably obtainable via Route 119 fishing. Add a Pacifidlog trade giving Feebas rather than Horsea, holding a Prism Scale; verify the updated Milotic evolution method.
- Fortree: Volbeat for one unchosen Hoenn starter. Battle Frontier: Skitty for the remaining unchosen starter. Both are one-time, starter-dependent rewards; decide whether actual trades or gifts. Test all three starter paths, Pokédex, OT/nickname and held items; remove Mail from trades if present.
- Replace mandatory trade evolutions with accessible Link Cable or item-only methods. Enable appropriate bag-use evolution items; validate prerequisites and species eligibility.
- Rayquaza capture gating is planned; exact relationship to story encounter and postgame challenge unlocks needs final definition.
- Later ideas: evolutions such as Probopass, Roserade and Togekiss; regional forms; Kanto content/maps; Mega Evolution. Do not expand the core required Hoenn Dex by accident.

### 4. Items, shops and progression
**Staged economy (issue #40; proposed prices in Pokédollars):**

| Milestone | Stock / reward |
|---|---|
| New game | One Oran Berry in PC (tested) |
| Petalburg Woods | Exp. Share from researcher (partially tested) |
| Peeko rescue | Everstone item ball in Rusturf Tunnel; stays until collected |
| Steven letter | Lucky Egg replacement reward (delivery test outstanding) |
| Slateport arrival | Heart Scale 250; Everstone 1,000 |
| Balance Badge / Norman | Eviolite 5,000 |
| Groudon/Kyogre crisis resolved | Air Balloon, Loaded Dice, Rare Candy: 1,000 each |
| Champion | PP Up 1,000; PP Max 3,000 or rare/gift-only |
| Champion + special Ditto gift | Destiny Knot 5,000 |

Lilycove: remove Mail from department store, consolidate TM sales at one clerk, sell Nature Mints; test Ability Capsule, Ability Patch and Link Cable (temporarily placed on Floor 4). Final Ability Patch access should be postgame only. Earlier discussion suggested a Mossdeep scientist gift/sales; reconcile NPC versus Lilycove vendor rather than enabling early HA access. Capsule may be available earlier. Confirm prices, correct bag pockets, nature stat effects, dialogue and reusable TMs.

Other discussed items/services: ORAS berries, Shiny Charm, Lucky Egg, EXP Candies, PP Ups, Repel, Eviolite, Air Balloon, reusable Escape Rope, and optional postgame Master Ball sales (5,000 proposed; not finalized). Free Move Relearner/Deleter and buyable Heart Scales were both discussed; reconcile whether the base service is free or costs a Heart Scale. HMs should be deletable; ride-like field prompts are desired.

### 5. Breeding and team preparation
- Early Rustboro Pokémon Nursery (or Devon Nursery): breeding only, no experience gain, no early Ditto, clear explanation. Normal Day Care near Mauville remains midgame. Preserve compatible-pair rules.
- Everstone reward after Peeko rescue: grunt discards a “useless stone”; visible persistent item ball avoids a bag-full story interruption. Nursery hints at nature inheritance.
- Postgame shiny foreign/Japanese Ditto if supported, good or perfect IVs (exact values TBD), Destiny Knot, suggested Lv. 30 and Poké Ball/Luxury Ball. One-time gift; unlocks Slateport Destiny Knot stock. Test Masuda-style compatibility and inheritance.
- Open #56–64: faster Egg generation; faster hatching (classic/modern toggle if practical); improved Everstone nature and Destiny Knot IV inheritance; easier Egg Move inheritance; Day Care compatibility/status information; useful Egg summary without inappropriate spoilers; item accessibility; stronger postgame breeding QoL.
- Open #65: make Mirror Herb obtainable and verify its breeding/Egg Move functionality. Open #66: optional male normal/Hidden Ability inheritance without Ditto, toggleable.
- Egg Move relearner linked to Nursery/Day Care progress; later tutor relearner. Verify modern same-species transfer to a Pokémon with an empty move slot.

### 6. Settings, interface and field tools
**Challenge Settings (#36):** separate from Assist Mode; selected at new game or early game, potentially locked after first badge. Battle Items: Allowed/Held Only; Fainting: Normal/Nuzlocke; Catch: Normal/First Encounter; Nicknames: Optional/Required; Level Cap: Off/Gym Leader Ace. Early Nuzlocke/catch implementation may be warnings/tracking rather than enforcement. Required nicknames cover catches, gifts and hatches. Cap all EXP, candy and Day Care sources.

Suggested caps: Roxanne 15; Brawly 19; Wattson 24; Flannery 29; Norman 31; Winona 33; Tate & Liza 42; Juan 46; League/Champion 58; no cap postgame. Reconcile caps with final trainer teams.

**Assist Mode (#37):** freely toggleable conveniences/testing options: Auto Heal After (Off/Battle/Level Up/Both); Infinite PP (restoration after encounters); No Wild Encounters (not fishing/static/scripted); One-Hit Capture (wild only); EXP and Money multipliers (1x/2x/4x); Always Shiny (force-shiny hook); Auto Run (Default/Always, optional B to walk); Bagon Encounters (Classic low-level/Improved level). Respect challenge caps and scripted sequences. Trainer sight disable is also a proposed hook. Other discussed toggles: low-HP beep, nickname prompting, cutscenes, obstacle cleanup after Champion, Master Ball access.

- Mute (#7): default Off, save-backed; suppress music, fanfares, cries, SFX where practical; restore correct map music when disabled.
- #23: prevent Poké Ball use in trainer battles, including last-ball shortcut; preserve Wally tutorial and scripted captures.
- #35: increase bag capacity across pockets; test save compatibility. After Hall of Fame Rydel upgrades access to both bikes, or a single Bike Kit toggle; test rails/hops/slopes/Safari Zone.
- #46: ORAS-style four-slot registered Key Item wheel, with ordinary Bag access retained; Bike Kit, reusable Escape Rope, Dowsing Machine, PokéNav, eventual Mega/form item. Test follower, dark cave and control interactions.
- #42: PokéNav area checklist with unique species, caught count, caught/seen/unseen status, optional spoiler-safe ???. Combine land, Surf, fishing, Rock Smash and future wild methods. Exclude gifts/trades/trainers/events unless specifically designed. Show completion message; test duplicate slots, no-encounter areas and Route 119 Feebas.
- DexNav: dedicated future milestone; check search/detector flags and Hidden Ability access (avoid bypassing planned HA gating).
- Field-action EXP (#28): optional, non-farmable; Cut 25, Rock Smash 25, Strength 75 once per meaningful puzzle/room in first pass; Flash 25 once per area proposed. No repeatable Surf/Dive/Waterfall rewards or postgame cleanup EXP. Choose lead/follower/action Pokémon; no fainted recipient, respect caps and safe evolution handling.

### 7. Battle systems and trainers
- Update gym and Elite Four teams (#31). Discussed candidates: Roxanne Aron/Rhyhorn; Wattson Raichu; Winona Crobat; Juan Crawdaunt/Sharpedo; Phoebe Gengar; Glacia Cloyster/Castform with weather. These are candidates, not final rosters. Norman Eviolite Vigoroth suggested. Replace repetitive four level-3 Wurmple Petalburg Woods trainer with Wurmple/Silcoon/Cascoon variety.
- Moves discussed: Bullet Seed, Tail Slap, Rock Blast, Triple Axel, Scale Shot; check existing upstream support and distribution.
- Guts + Flame Orb + Facade regression (#9): Taillow/Swellow; end-turn burn, Guts attack increase, Facade doubled power under relevant status, burn attack penalty bypass under Guts. Toxic Orb optional later.
- Frontier tutor hub (#33): Drain Punch, Knock Off, Ice/Thunder/Fire Punch, Seed Bomb, Gunk Shot, Iron Head, Zen Headbutt, Scale Shot, Triple Axel. Suggested BP prices: 24 for punches/Seed Bomb; 32 for Drain Punch/Knock Off/Iron Head/Zen Headbutt; 40 for Gunk Shot/Scale Shot/Triple Axel. BP broker: 1,000 money per BP (bundles 1/5/10/50). Hidden Power type changing service; exact costs and legal behavior to verify. Postgame only.
- Poké Ball stylist (#34): choose Pokémon and consume a target ball; keep all other Pokémon data unchanged. No Eggs; cannot transfer into Master Ball; removing Pokémon from Master Ball returns it to bag per issue note. Decide special/event ball rules, PC selection and full-bag handling.
- Recovery courier (#27): recover failed wild capture balls into pending storage at 50% Poké Ball, 40% Great Ball, 30% Ultra Ball, 25% special, 0% Master Ball; reclaim via NPC, preserve pending stock if bag full. No successful/trainer captures; scripted exceptions TBD.

### 8. Home, friendship, flavor and postgame
- Mom's fridge (#38): after Badge 1, five random berries once daily (duplicates allowed); early Oran/Pecha/Cheri/Chesto/Rawst/Aspear/Persim; after Norman add Lum/Sitrus/EV-reducing/contest berries; rare berries postgame. Handle bag full and RTC/fake RTC resets.
- Mom's Care (#45): earn one charge per badge, cap two; heal team and give +2/+3 friendship to non-Egg party Pokémon. Hall of Fame clears can replenish after Badge 8. Save-backed charges. Friendship Checker (#26, also #45) retains normal rating and can encourage one chosen non-Egg Pokémon daily; +2 recommended, no increase at max friendship. Consolidate overlapping issues rather than implementing twice.
- Mom battle (#39): after Rayquaza caught/defeated, preferably also Champion. At Littleroot home, reveals she challenged League. Manectric, Gardevoir, Milotic, Altaria, Delcatty, Absol. Suggested Lv. 70–74 first, 78–82 rematch. Warm optional challenge; PP Max first win, rare berries repeat reward proposed; daily/rematch rules TBD.
- Birch battle (#30): Champion and Rayquaza gate; all three Hoenn starters, Crobat, Gardevoir, Aggron; suggested Lv. 68–72, later rematch 78–82. Optional PP Max/Ability Capsule/rare berry reward; not required for Hoenn completion.
- Aurora Ticket (#21): one-time post-Champion Key Item, candidate Mossdeep Space Center NPC or harbor/ticket counter; enable S.S. Tidal/Birth Island travel and normal puzzle/Deoxys capture; nonconsumable, no external event. Verify return travel and one-time event. Jirachi postgame access also discussed; exact event TBD.
- Bill postgame (#32): appearance, National Dex records, Eevee gift and Box Link upgrade. Later expansion of Eevee gifts possible; exact unlocks and repeatability need review.
- Optional flavor (#8): Classic/Verdant setting for short funny save/PC/healing/escape/follower/berry/Exp. Share messages. Preserve serious scenes and clear gameplay information.
- Regional Easter eggs (#29): Tera Shard researcher; distant Corsola, Zigzagoon, snowy Sandshrew/Vulpix, Meowth, Geodude, Ponyta, Farfetch'd references; Winona steel bird hint, Wally Kirlia alternate form, Gengar floating joke, Ditto/slime joke, partner Champion reaction. Prefer caught-status reactions; do not imply unobtainable forms are available.

### 9. Branding and visual polish
Pokémon Verdant is the current project name. An earlier title proposal replaced EMERALD VERSION with VERDANT VERSION while retaining Rayquaza and crediting upstream; another historical option was POKÉMON EMERALD VERDANT. The November conversation favored an option 3 distinct from Pokémon Sage, but its exact artwork description could not be recovered; do not treat the earlier June option as the same choice.

- #44: custom title card/branding after gameplay stability, branch `custom-title-screen` suggested; start with logo, animation later. Test intro, title, new game, continue and palettes.
- #24: replace load/continue Pokémon; candidates Treecko line, Torchic/Flare, Ralts/Gardevoir, Rayquaza or custom mascot. No final selection verified.
- Possible later artist commission shared across multiple ROM hack projects if the artist's work is liked; Verdant should maintain a distinct identity from Sage. No commission or final asset direction confirmed.
- Keep credits for pret and RH-Hideout/pokeemerald-expansion; distinguish upstream features from Verdant-specific changes in documentation.

### 10. Companion site and shared Pokémon Builder
Earlier plan: Next.js Verdant companion website with a ROM export script, route/encounter JSON, Hoenn Dex data, Pokémon details and sprite pipeline (#11–20). `pokemon.json` canonical species data for all 202 Emerald Hoenn entries; remove duplicated locations; encounter/trainer/event records reference stable National Dex IDs. Route guides show method, species, rate and availability when available. Add gifts, trades, evolution conditions, item access, trainer teams, progression and postgame information as data matures.

Later decision: overhaul `pokemon-builder-public` first, then add Verdant as a first-class custom game profile in the shared SQLite-backed builder rather than a separate official generation or duplicate team builder. `games.base_game_id` references Emerald; profile-specific Pokédex, mechanics, availability and progression. Explicit form-based evolution rows (`from_form_id`, `to_form_id`, method, level/item/notes) rather than inferring evolution from Dex order. Existing builder DB had generations, games and sprite_sets at the time of discussion; further schema work needed.

Builder requirements (#47–55): schema, team builder page, six slots, search/picker modal, weakness/resistance analysis, earliest location/availability for team members, badge-progress filter, shareable team URL. PokéAPI sprites preferred for website and builder: Gen III Emerald sprites where possible; small icons or official art depending on UI; item sprites, fallback and variants, credits and usage/license review. Source: https://github.com/PokeAPI/sprites

Website and builder issue ownership may need moving/relabeling after the shared-builder decision; do not create duplicate tickets automatically.

### 11. Technical implementation and testing
Mac development setup discussed June 21: install Xcode command-line tools (`xcode-select --install`) and Homebrew; core packages `make automake autoconf libtool pkg-config`; build tools `cmake ninja`; asset libraries `libpng libjpeg-turbo libogg libvorbis`; helpers `wget unzip`. Install devkitPro pacman package from https://github.com/devkitPro/pacman/releases; macOS Privacy & Security approval may be needed. Commands discussed: `sudo dkp-pacman -Sy`, `sudo dkp-pacman -S gba-dev`, `sudo dkp-pacman -S devkitarm-rules`. Configure `DEVKITPRO=/opt/devkitpro` and `DEVKITARM=$DEVKITPRO/devkitARM` in `~/.zshrc`. These are historical setup notes, not a freshly verified installation guide. A blog post describing the setup was planned.

#25 feature flags: define unique unused constants in `include/constants/flags.h`; do not reuse Exp. Share flag. Proposed config links:

```c
#define P_FLAG_EGG_MOVES FLAG_UNLOCK_EGG_MOVE_RELEARNER
#define P_FLAG_TUTOR_MOVES FLAG_UNLOCK_TUTOR_MOVE_RELEARNER
#define P_SORT_MOVES TRUE
#define OW_FLAG_POKE_RIDER FLAG_UNLOCK_POKE_RIDER
#define OW_FLAG_NO_TRAINER_SEE FLAG_DISABLE_TRAINER_SIGHT
#define P_FLAG_FORCE_SHINY FLAG_FORCE_SHINY_MODE
#define P_FLAG_FORCE_NO_SHINY FLAG_FORCE_NO_SHINY_MODE
#define DN_FLAG_DEXNAV_GET FLAG_UNLOCK_DEXNAV
#define DN_FLAG_DETECTOR_MODE FLAG_DEXNAV_DETECTOR_MODE
#define DN_FLAG_SEARCHING FLAG_DEXNAV_SEARCHING
```

Summary EV/IV access, sorted moves, relearner progression, Poké Rider/map Fly after Fly, Assist-only trainer sight and shiny hooks, DexNav dedicated tests. Verify current upstream macro names before implementing. Save-backed settings and flags require save/load tests, new-game default checks and migration/new-save policy. Regression priorities: one-time reward duplication, bag-full cases, wild vs trainer vs scripted battles, all three starter choices, cap interactions, RTC reset, event gates and map travel. Test builds and patch distribution separately; avoid calling an issue implemented solely because it was closed.

### 12. Roadmap and milestones
Historical proposed milestone names: Verdant QoL & Interface; Challenge & Assist; Early/Midgame Rewards & Economy; Postgame Events & Gifts; DexNav/PokéNav Tools; Flavor & Visual Polish; Battle Systems & Balance; companion documentation website; team builder. The live milestone list could not be retrieved; these are historical themes, not confirmed current GitHub titles or release dates.

Verified numeric assignments from individual issue records: milestone #1 contains issues 1–6; #2 contains 11–12; #4 contains 7; #6 contains 10; #9 contains 8; #10 contains 9; #11 contains 47; #12 Breeding improvements (issues #56–64). Other assignments, milestone state and completion totals were not verified. Live list: https://github.com/jennifert/pokeemerald-expansion/milestones

Suggested sequencing (editorial synthesis, not a committed version plan):
1. Core regression: finish #1–3 and #6, establish one-save availability and stable save/config flags.
2. Early and midgame rewards/economy, evolution access, breeding progression and item placement.
3. Challenge/Assist, inventory and field QoL; test interactions.
4. Postgame rewards, starter access, special events, family/Birch battles, Bill and Frontier services.
5. PokéNav/DexNav and interface enhancements; companion site/data exports can develop alongside stable game data. Shared builder integration follows builder overhaul.
6. Visual and flavor polish; title/continue assets last. Later features remain “Ideas for Future Updates” rather than commitments.

### 13. Complete GitHub issue register
All 66 issue numbers and titles below were retrieved via the GitHub connector. Open/closed states were independently queried. Links use the actual repository issue numbers. Detailed design summaries above consolidate available issue bodies and earlier project discussions; they are not verbatim exports of every checklist or comment.

**Current issue summary:** 66 total — 64 open, 2 completed.

| Issue | Title | Status | Verified milestone |
|---|---|---|---|
| [#1](https://github.com/jennifert/pokeemerald-expansion/issues/1) | Test Hoenn Dex availability and updated wild encounters | Open | 1 |
| [#2](https://github.com/jennifert/pokeemerald-expansion/issues/2) | Test Lilycove Dept. Store and item access changes | Open | 1 |
| [#3](https://github.com/jennifert/pokeemerald-expansion/issues/3) | Test expansion config and QoL feature updates | Open | 1 |
| [#4](https://github.com/jennifert/pokeemerald-expansion/issues/4) | Fix early-route Zigzagoon encounter rate | Closed – completed | 1 |
| [#5](https://github.com/jennifert/pokeemerald-expansion/issues/5) | Add Oran Berry to player PC before first rival battle | Closed – completed | 1 |
| [#6](https://github.com/jennifert/pokeemerald-expansion/issues/6) | Move Exp. Share reward to Petalburg Woods and replace Steven letter reward | Open | 1 |
| [#7](https://github.com/jennifert/pokeemerald-expansion/issues/7) | Add simple mute option to Start Menu settings | Open | 4 |
| [#8](https://github.com/jennifert/pokeemerald-expansion/issues/8) | Add optional Verdant flavor messages | Open | 9 |
| [#9](https://github.com/jennifert/pokeemerald-expansion/issues/9) | Future test: Guts + Flame Orb + Facade package | Open | 10 |
| [#10](https://github.com/jennifert/pokeemerald-expansion/issues/10) | Add Everstone reward after Peeko rescue | Open | 6 |
| [#11](https://github.com/jennifert/pokeemerald-expansion/issues/11) | Scaffold Next.js companion site | Open | 2 |
| [#12](https://github.com/jennifert/pokeemerald-expansion/issues/12) | Create ROM data export script | Open | 2 |
| [#13](https://github.com/jennifert/pokeemerald-expansion/issues/13) | Generate clean route encounter JSON | Open | — |
| [#14](https://github.com/jennifert/pokeemerald-expansion/issues/14) | Build route guide page layout | Open | — |
| [#15](https://github.com/jennifert/pokeemerald-expansion/issues/15) | Render wild encounters by method | Open | — |
| [#16](https://github.com/jennifert/pokeemerald-expansion/issues/16) | Add route/location index page | Open | — |
| [#17](https://github.com/jennifert/pokeemerald-expansion/issues/17) | Generate Hoenn Pokédex JSON | Open | — |
| [#18](https://github.com/jennifert/pokeemerald-expansion/issues/18) | Build Hoenn Dex list page | Open | — |
| [#19](https://github.com/jennifert/pokeemerald-expansion/issues/19) | Build basic Pokémon detail page | Open | — |
| [#20](https://github.com/jennifert/pokeemerald-expansion/issues/20) | Add sprites/icons/assets pipeline | Open | — |
| [#21](https://github.com/jennifert/pokeemerald-expansion/issues/21) | Add Aurora Ticket as a postgame Key Item | Open | — |
| [#22](https://github.com/jennifert/pokeemerald-expansion/issues/22) | Add postgame shiny foreign Ditto gift and Destiny Knot shop unlock | Open | — |
| [#23](https://github.com/jennifert/pokeemerald-expansion/issues/23) | Disable Poké Balls in Trainer Battles | Open | — |
| [#24](https://github.com/jennifert/pokeemerald-expansion/issues/24) | Change Pokémon shown on load/continue screen | Open | — |
| [#25](https://github.com/jennifert/pokeemerald-expansion/issues/25) | Define Verdant feature unlock flags and config hooks | Open | — |
| [#26](https://github.com/jennifert/pokeemerald-expansion/issues/26) | Let Friendship Checker give one daily encouragement message | Open | — |
| [#27](https://github.com/jennifert/pokeemerald-expansion/issues/27) | Add Poké Ball Recovery Courier | Open | — |
| [#28](https://github.com/jennifert/pokeemerald-expansion/issues/28) | Add field action EXP rewards | Open | — |
| [#29](https://github.com/jennifert/pokeemerald-expansion/issues/29) | Add regional flavor and easter egg NPC messages | Open | — |
| [#30](https://github.com/jennifert/pokeemerald-expansion/issues/30) | Add postgame Professor Birch battle | Open | — |
| [#31](https://github.com/jennifert/pokeemerald-expansion/issues/31) | Update Gym Leader and Elite Four teams | Open | — |
| [#32](https://github.com/jennifert/pokeemerald-expansion/issues/32) | Add postgame Bill appearance, National Dex records, Eevee gift, and Box Link upgrade | Open | — |
| [#33](https://github.com/jennifert/pokeemerald-expansion/issues/33) | Add Battle Frontier postgame move tutors, BP broker, and Hidden Power service | Open | — |
| [#34](https://github.com/jennifert/pokeemerald-expansion/issues/34) | Add Pokémon Center Poké Ball changing service | Open | — |
| [#35](https://github.com/jennifert/pokeemerald-expansion/issues/35) | Add expanded bag space and late-game bike QoL | Open | — |
| [#36](https://github.com/jennifert/pokeemerald-expansion/issues/36) | Add Challenge Settings screen | Open | — |
| [#37](https://github.com/jennifert/pokeemerald-expansion/issues/37) | Add Assist Mode settings screen | Open | — |
| [#38](https://github.com/jennifert/pokeemerald-expansion/issues/38) | Add daily berry reward from Mom’s fridge | Open | — |
| [#39](https://github.com/jennifert/pokeemerald-expansion/issues/39) | Add postgame Mom battle after Rayquaza | Open | — |
| [#40](https://github.com/jennifert/pokeemerald-expansion/issues/40) | Update Slateport Market and Lilycove item availability | Open | — |
| [#41](https://github.com/jennifert/pokeemerald-expansion/issues/41) | Update Emerald in-game trades with Feebas and unchosen starter gifts | Open | — |
| [#42](https://github.com/jennifert/pokeemerald-expansion/issues/42) | Add PokéNav area checklist view | Open | — |
| [#43](https://github.com/jennifert/pokeemerald-expansion/issues/43) | Rustboro Nursery and Breeding Progression | Open | — |
| [#44](https://github.com/jennifert/pokeemerald-expansion/issues/44) | Custom Title Screen Card | Open | — |
| [#45](https://github.com/jennifert/pokeemerald-expansion/issues/45) | Mom's Care and Friendship Rituals | Open | — |
| [#46](https://github.com/jennifert/pokeemerald-expansion/issues/46) | ORAS-Style Key Item Wheel | Open | — |
| [#47](https://github.com/jennifert/pokeemerald-expansion/issues/47) | Define team builder data schema | Open | 11 |
| [#48](https://github.com/jennifert/pokeemerald-expansion/issues/48) | Create team builder page | Open | — |
| [#49](https://github.com/jennifert/pokeemerald-expansion/issues/49) | Add six team slots | Open | — |
| [#50](https://github.com/jennifert/pokeemerald-expansion/issues/50) | Build Pokémon search/picker modal | Open | — |
| [#51](https://github.com/jennifert/pokeemerald-expansion/issues/51) | Implement type weakness/resistance analysis | Open | — |
| [#52](https://github.com/jennifert/pokeemerald-expansion/issues/52) | Show availability and earliest location for team members | Open | — |
| [#53](https://github.com/jennifert/pokeemerald-expansion/issues/53) | Add badge/progress availability filter | Open | — |
| [#54](https://github.com/jennifert/pokeemerald-expansion/issues/54) | Add shareable team URL | Open | — |
| [#55](https://github.com/jennifert/pokeemerald-expansion/issues/55) | Use PokéAPI sprites for website and team builder | Open | — |
| [#56](https://github.com/jennifert/pokeemerald-expansion/issues/56) | Add faster Egg generation at the Day Care | Open | — |
| [#57](https://github.com/jennifert/pokeemerald-expansion/issues/57) | Add faster Egg hatching | Open | — |
| [#58](https://github.com/jennifert/pokeemerald-expansion/issues/58) | Improve Everstone nature inheritance | Open | — |
| [#59](https://github.com/jennifert/pokeemerald-expansion/issues/59) | Improve Destiny Knot IV inheritance | Open | — |
| [#60](https://github.com/jennifert/pokeemerald-expansion/issues/60) | Improve Egg Move inheritance | Open | — |
| [#61](https://github.com/jennifert/pokeemerald-expansion/issues/61) | Add Day Care breeding information | Open | — |
| [#62](https://github.com/jennifert/pokeemerald-expansion/issues/62) | Add Egg summary information | Open | — |
| [#63](https://github.com/jennifert/pokeemerald-expansion/issues/63) | Improve breeding item accessibility | Open | — |
| [#64](https://github.com/jennifert/pokeemerald-expansion/issues/64) | Add postgame advanced breeding QoL | Open | — |
| [#65](https://github.com/jennifert/pokeemerald-expansion/issues/65) | Mirror Herb addition | Open | — |
| [#66](https://github.com/jennifert/pokeemerald-expansion/issues/66) | Optional male Ability/HA inheritance without Ditto | Open | — |

### 14. Open decisions and maintenance notes
- Confirm actual milestone titles, states, issue assignments, labels and PR/branch/release inventory directly in GitHub. Search returned null milestone/label fields; individual issue retrieval was limited. Companion-site repository search returned an access/not-found error. No GitHub records were changed.
- Issues #56–64 were reopened and retained under Milestone 12. Review existing upstream breeding mechanics before implementation to distinguish configuration changes, custom enhancements, and regression testing.
- Decide final HA access NPC, cost and stock; verify trade evolution scheme, Milotic method and starter trade/gift details. Choose Rayquaza gating, Jirachi event and Bill specifics.
- Reconcile overlapping #26/#45 friendship design and website/builder issues after architectural decision. Verify title screen option selected in November and final mascot. Establish final gym/League teams and level caps.
- Confirm whether proposed future mechanics and item placements are still desired before coding. Mark each feature as planned, implemented, tested, deferred or dropped in future updates.

### 15. Source and coverage notes
Primary sources: project discussion summaries and retrieved earlier conversations (June–November 2026), portfolio and builder database context, GitHub issue search and individual issue records for the main fork. Repository links above provide the live source of truth. The issue index is complete for the 66 results retrieved, but the document is not an exhaustive export of all chats, full issue bodies, comments, milestones, labels, branches, commits, pull requests or repository files. No source-code/build inspection was performed. Proposed sequencing and section organization are editorial choices for a living development reference.
