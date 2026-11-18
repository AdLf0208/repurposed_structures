# Licence notice — Repurposed Structures (outposts and witch huts), Horizon port

**The port is licensed under the GNU Lesser General Public License, version 3.0
only**, the licence of the mod it carries. The full text is beside this file as
`LICENSE` (and inside the package at
`data/repurposed_structures/license.txt`).

## Where the licence was read

- The jar **`repurposed_structures-7.5.22+1.21.1-neoforge.jar`** (Modrinth
  project `QDNS5oAT`, version `8duZuWci`; sha1
  `a64f6b2d331d5c3a5feefcd18d23f4585a42b097`, sha256
  `64e64109acf7673b969aca9b3cca0bb555777cd7038aa16aa32a1548d753f257`), file
  `META-INF/neoforge.mods.toml`:

  ```toml
  license="https://github.com/TelepathicGrunt/RepurposedStructures/blob/latest-released/LICENSE"
  ```

  The jar ships no `LICENSE` file of its own; the field names the repository's
  licence file, which is the **GNU Lesser General Public License v3.0** (the
  repository's `LICENSE` and `gradle.properties` agree). Recorded from the jar
  first, as the campaign requires.

- The source-map row in `ports/_shared/source-map/atm10-sources.csv` also
  records `LGPL-3.0-only` (licence rank 1: copyleft, publishable under the same
  licence with the complete corresponding source).

## What was taken

Only the mod's **data**: `data/repurposed_structures/worldgen/**`,
`data/repurposed_structures/structure/**` (structure templates), its biome and
structure-set tags, its outpost loot tables and the placed feature its End
outpost names. No Java code is read, copied or translated; the rewrites the
carry applies are Horizon's documented data mappings (`docs/modpacks.md`), not
mod code.

The templates and loot tables are carried **byte-identical** to the jar. The
worldgen JSON is the mod's own with only the rewrites `tools/carry.py` lists
(and `notes.md` records).

## Attribution

Repurposed Structures is by **TelepathicGrunt** (the jar's `authors` field),
with credits to `/r/l-ll-ll-l_IsDisLoss`, miguelforge and cannon_foddr for
donated structures. This port is an **alteration** of that mod's data for
Horizon (Minecraft 26.3): it carries a subset of the mod's structures and
rewrites the worldgen types the target cannot read.

## Corresponding source

The port's complete corresponding source is this directory: `tools/carry.py`
(the carry), `tools/verify.py`, `content/` and `notes.md`. Rebuilding the
package from the same jar reproduces it byte for byte.
