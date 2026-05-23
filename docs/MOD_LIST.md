# TBS-Server mod list

Reference for every entry tracked by packwiz in this pack. Source of truth is the
`.pw.toml` files under `mods/` — when those change, this doc should be updated
alongside `README.md` and `CHANGELOG.md`.

- Tier rationale: [`TBS-mod-strategy.md`](TBS-mod-strategy.md)
- Vanilla-client contract: see [`../README.md`](../README.md)
- Target: **Minecraft 26.1.2 (Fabric 1.x)**
- Pack version: see [`pack.toml`](../pack.toml)

**Total:** 26 mods. Every mod is server-side or `both` and either touches no
client-visible content or shares an optional companion with TBS-Client.

Reference links resolve to the project page on the listed source; CurseForge
project-ID URLs redirect to the canonical slug.

## Tier S1 — Performance core

| Mod | Side | Source | Filename |
|---|---|---|---|
| [Fabric API](https://modrinth.com/mod/P7dR8mSH) | both | Modrinth | `fabric-api-0.149.1+26.1.2.jar` |
| [Lithium](https://www.curseforge.com/projects/360438) | both | CurseForge | `lithium-fabric-0.24.2+mc26.1.2.jar` |
| [Krypton](https://www.curseforge.com/projects/428912) | both | CurseForge | `krypton-0.3.0.jar` |
| [FerriteCore](https://modrinth.com/mod/uXXizFIs) | both | Modrinth | `ferritecore-9.0.0-fabric.jar` |
| [C2ME — Concurrent Chunk Management Engine](https://www.curseforge.com/projects/533097) | both | CurseForge | `c2me-fabric-mc26.1.2-0.3.7+alpha.0.68.jar` |
| [Chunky](https://modrinth.com/mod/fALzjamp) | both | Modrinth | `Chunky-Fabric-1.5.3.jar` |

## Tier S2 — Observability & operations

| Mod | Side | Source | Filename |
|---|---|---|---|
| [spark](https://www.curseforge.com/projects/361579) | both | CurseForge | `spark-1.10.172-fabric.jar` |
| [Connectivity](https://www.curseforge.com/projects/470193) | both | CurseForge | `connectivity-fabric-26.1-7.6.jar` |
| [Ledger](https://www.curseforge.com/projects/491137) | both | CurseForge | `ledger-1.3.20.jar` |

## Tier S3 — Permissions & admin

| Mod | Side | Source | Filename |
|---|---|---|---|
| [LuckPerms](https://www.curseforge.com/projects/431733) | both | CurseForge | `LuckPerms-Fabric-5.5.42.jar` |
| [Vanilla Permissions](https://modrinth.com/mod/fdZkP5Bb) | server | Modrinth | `vanilla-permissions-0.3.6+26.1.2.jar` |
| [WorldEdit](https://www.curseforge.com/projects/225608) | both | CurseForge | `worldedit-mod-7.4.3.jar` |

> "Essential Permissions" in [`TBS-mod-strategy.md`](TBS-mod-strategy.md) was
> re-sourced from Modrinth as **Vanilla Permissions** in commit `fcc5cc7` —
> same role, different upstream name.

## Tier S4 — Communication

| Mod | Side | Source | Filename |
|---|---|---|---|
| [Text Placeholder API](https://www.curseforge.com/projects/1037459) | both | CurseForge | `placeholder-api-3.0.0+26.1.jar` |
| [Styled Chat](https://www.curseforge.com/projects/493348) | both | CurseForge | `styled-chat-2.12.0+26.1.2.jar` |

## Tier S5 — Gameplay augmentation (vanilla-packet-only)

| Mod | Side | Source | Filename |
|---|---|---|---|
| [Better Server Sleep](https://modrinth.com/mod/z9nwMi0g) | both | Modrinth | `better-serversleep-26.1.jar` |
| [Lootr](https://modrinth.com/mod/EltpO5cN) | both | Modrinth | `lootr-fabric-26.1.2-1.22.36.109.jar` |
| [FallingTree](https://www.curseforge.com/projects/349559) | both | CurseForge | `FallingTree-26.1.2-25.jar` |
| [Saplanting](https://www.curseforge.com/projects/576864) | both | CurseForge | `saplanting-fabric-26.1.2-1.3.1.jar` |
| [Universal Bone Meal](https://www.curseforge.com/projects/594013) | both | CurseForge | `UniversalBoneMeal-v26.1.0-mc26.1.x-Fabric.jar` |
| [Trade Cycling](https://www.curseforge.com/projects/570431) | both | CurseForge | `trade-cycling-fabric-1.0.21+26.1.2.jar` |

## Tier S6 — Discoverability

| Mod | Side | Source | Filename |
|---|---|---|---|
| [BlueMap](https://www.curseforge.com/projects/406463) | both | CurseForge | `bluemap-5.20-fabric.jar` |

## Tier S7 — Cross-side (shared with TBS-Client, must match versions)

| Mod | Side | Source | Filename |
|---|---|---|---|
| [Simple Voice Chat](https://modrinth.com/mod/9eGKb6K1) | both | Modrinth | `voicechat-fabric-2.6.17+26.1.2.jar` |

> **StreamCraft Live** is the second cross-side mod per
> [`TBS-mod-strategy.md`](TBS-mod-strategy.md) but is **not** in this packwiz
> manifest — it is shipped independently (see `../StreamCraftLive/`) and pinned
> to the same version on TBS-Client. The `v1.0.2` release bundles
> StreamCraft 0.8.22.

## Library dependencies (not in a named tier)

Required by mods above.

| Mod | Side | Source | Filename |
|---|---|---|---|
| [Fabric Language Kotlin](https://www.curseforge.com/projects/308769) | both | CurseForge | `fabric-language-kotlin-1.13.11+kotlin.2.3.21.jar` |
| [Cupboard](https://www.curseforge.com/projects/326652) | both | CurseForge | `cupboard-fabric-26.1-3.7.jar` |
| [Forge Config API Port](https://www.curseforge.com/projects/547434) | both | CurseForge | `ForgeConfigAPIPort-v26.1.4-mc26.1.x-Fabric.jar` |
| [Puzzles Lib](https://www.curseforge.com/projects/495476) | both | CurseForge | `PuzzlesLib-v26.1.8-mc26.1.x-Fabric.jar` |

## Pending — no 26.1.2 build yet

From [`TBS-mod-strategy.md`](TBS-mod-strategy.md). The architecture absorbs
server-side gaps cleanly, so these will be added incrementally as builds appear,
with no TBS-Client change required:

- **ModernFix** — load-time / memory fixes (S1)
- **Noisium** — worldgen chunk perf (S1)
- **Advanced Backups** — differential world backups (S2)
- **AutoWhitelist** — Discord-role-linked whitelist sync (S2)
- **Gamemode Unrestrictor** — flexible `/gm` (S3)
- **Fabricord** — two-way Discord ↔ in-game chat bridge (S4)
- **NoExpensive** — removes the anvil "Too Expensive" cap (S5)

`luckperms-placeholders` (S3) was not found on CurseForge or Modrinth under that
name — LuckPerms group/prefix data is already exposed to chat via Styled Chat +
Text Placeholder API (both installed). Confirm whether a separate bridge mod is
still wanted.
