# TBS-Server

**The Block Survival — Server modpack**

Fabric 1.x modpack for **Minecraft 26.1.2**, built with [packwiz](https://packwiz.infra.link/).
Deployed to the game server via [mrpack4server](https://github.com/Patbox/mrpack4server).

TBS-Server makes the server fast, observable, well-administered, and gameplay-rich **while
staying joinable by any vanilla 26.1.2 client** (with only StreamCraft installed).

## The vanilla-client contract

The base server is vanilla 26.1.2. Every server mod must either:

1. **Add no new client-visible content** — it changes how vanilla mechanics behave (sleep
   voting, tree-felling, anvil costs, trade restocking) without introducing new
   blocks/items/entities/packets. **Every v1.0 gameplay mod takes this path.**
2. **Translate new content into vanilla packets** via a library like Polymer. v1.0 ships no
   mods of this kind.

Two mods are shared with TBS-Client — **StreamCraft Live** and **Simple Voice Chat** —
each shipped at the same version on both sides. Both are optional per player: a vanilla
client without them still connects and plays. See `docs/TBS-mod-strategy.md` for the full
design.

## Deploy

One-click deploy from the TBS project root via `server-config.py`:

```bash
python ../server-config.py deploy        # export -> SFTP upload -> restart Bloom.host
python ../server-config.py               # interactive menu (deploy, power, backups)
```

It exports this pack, uploads the `.mrpack` to Bloom.host as `local.mrpack`, removes any
remote `modpack-info.json` so mrpack4server uses the local file, then restarts the server.
Needs `TBS/.env` (copy from `TBS/.env.example`).

Manual equivalent:

```bash
./packwiz.exe modrinth export            # produce TBS-Server-X.Y.Z.mrpack
# -> upload as local.mrpack to the host running mrpack4server
```

## Build / maintenance

```bash
./packwiz.exe cf install <mod-slug> -y   # add a mod from CurseForge (preferred)
./packwiz.exe mr install <mod-slug> -y   # Modrinth fallback (no CF 26.1.2 build)
./packwiz.exe update --all               # update every mod
./packwiz.exe refresh                     # rebuild index.toml after manual edits
```

CurseForge is always tried first; Modrinth is used only when a mod has no CurseForge build
for 26.1.2.

## Mod tiers

See `CHANGELOG.md` for the exact resolved state of every mod and `docs/TBS-mod-strategy.md`
for the full design rationale.

- **Tier S1 — Performance core:** Fabric API, Lithium, Krypton, FerriteCore, C2ME, Chunky
- **Tier S2 — Observability & operations:** Spark, Connectivity, Ledger
- **Tier S3 — Permissions & admin:** LuckPerms, Essential Permissions, WorldEdit
- **Tier S4 — Communication:** Text Placeholder API, Styled Chat
- **Tier S5 — Gameplay augmentation (vanilla-packet-only):** Better Server Sleep, Lootr,
  FallingTree, Saplanting, Universal Bone Meal, Trade Cycling
- **Tier S6 — Discoverability:** BlueMap
- **Tier S7 — Cross-side:** StreamCraft Live, Simple Voice Chat

## Pending mods

These mods from the strategy doc have **no 26.1.2 build** on CurseForge or Modrinth yet. Per
the strategy doc, the architecture absorbs server-side gaps cleanly — they will be added
incrementally as builds appear, with no TBS-Client change required:

- **ModernFix** — load-time / memory fixes (S1)
- **Noisium** — worldgen chunk perf (S1)
- **Advanced Backups** — differential world backups (S2)
- **AutoWhitelist** — Discord-role-linked whitelist sync (S2)
- **Gamemode Unrestrictor** — flexible `/gm` (S3)
- **Fabricord** — two-way Discord ↔ in-game chat bridge (S4)
- **NoExpensive** — removes the anvil "Too Expensive" cap (S5)

`luckperms-placeholders` (S3) was not found on CurseForge or Modrinth under that name —
LuckPerms group/prefix data is exposed to chat through Styled Chat + Text Placeholder API,
which are installed. Confirm whether a separate bridge mod is still wanted.

## Substitutions to confirm

- **Better Sleep** (doc, "percentage-based sleep voting") resolved to **Better Server Sleep**
  on Modrinth — verify it matches the intended behavior.

## Version coupling

TBS-Client and TBS-Server versions are **decoupled** — the mods whose versions must match
across both packs are **StreamCraft Live** and **Simple Voice Chat**. Coordinate bumps of
either as a synchronized release of both packs.
