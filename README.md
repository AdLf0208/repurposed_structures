# Repurposed Structures — a Horizon port

**Repurposed Structures** is a Minecraft mod. Reusing and modifying vanilla structures for extra variety!. This repository is a **port of it to [Horizon](https://github.com/horizon-rust/horizon)**, the Rust engine for Minecraft Java 26.3. It carries the complete source of the port plus the content files it ships, and installs as a single `.hmod` package.

Upstream: [TelepathicGrunt/RepurposedStructures](https://github.com/TelepathicGrunt/RepurposedStructures) — licence **LGPL-3.0-only**.

| | |
|---|---|
| Upstream mod | Repurposed Structures ([source](https://github.com/TelepathicGrunt/RepurposedStructures)) |
| Ported to | Horizon 0b14f8a, Minecraft Java 26.3, mod API `0.2` |
| Package | `repurposed_structures.hmod` (install it with the Horizon launcher) |
| Licence | **LGPL-3.0-only** — the upstream mod's licence; see [Licence and credit](#licence-and-credit) |

## What this port implements

The port's behaviour is recorded in the repository's `notes.md` (the campaign's per-mod record); this slice ships what that file describes.

## Not yet ported

- **The rest of the mod is not carried.** Mansions and monuments (12) have no
- **Structure `spawn_overrides` are not read for a mod's structures.** The
- **The End outpost spawns no shulkers.** `outposts/end/shulker_pool` names
- **`remove` keys in biome tags are ignored** by the content loader (it merges
- **`y_allowance` no longer clips pieces.** The game keeps `min_y`/`max_y` as
- **No `horizon:piece_limited.pieces`.** The outpost and witch-hut families
- **Advancements, `structure_map_trades`, `loot_modifiers`, `rs_spawners`,

## Installing

1. Install the [Horizon launcher](https://github.com/horizon-rust/horizon/releases) (0.2.70 or newer).
2. Add `repurposed_structures.hmod` to the instance's mods.
3. The package is pinned to a specific Horizon build; the launcher checks that pin.

## Licence and credit

Repurposed Structures was created by its upstream authors; the code, models and assets in the original mod
remain theirs and are used here under **LGPL-3.0-only**. The Rust in this repository is a clean-room
rewrite for Horizon, not a translation of the original source.

- `LICENSE` — the upstream licence text.
- `LICENSE-NOTICE.md` — what this port carries and where it came from.
- The upstream project: https://github.com/TelepathicGrunt/RepurposedStructures

## Technical details

```
horizon-mod.toml   package manifest (id, version, api, [native] pin)
Cargo.toml         the crate; depends on `horizon-mod-api` from the fetched SDK
src/               lib.rs (the one `impl Hooks`), runtime.rs (pure logic + tests), glue
assets/ data/      the content the package ships
tools/             content generators and the e2e scenario
```

- Build: `cargo horizon-mod build` (packages; it does not compile against the game).
- Test: `cargo test`, `cargo clippy --all-targets -- -D warnings`.
- In-game: `ports/tools/launcher-game.sh run repurposed_structures` in the campaign tree, or install the
  `.hmod` and play; the harness scenario is `tools/e2e.sh`.

This repository is generated from the campaign's port at `ports/repurposed_structures/`; the port's own
`notes.md` is the full record (decisions, traps, evidence).
