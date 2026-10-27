# mmTVAdapters

Third-party **standalone** macOS adapters for the [mmTV](https://github.com/Chiuvenz/mmTV) living-room shell.

mmTV is a launcher: it detects installed apps by Bundle ID and opens them. Adapter source, fetch/build/smoke scripts, and Electron runtimes live **here**, not inside the mmTV binary.

Physical remotes stay in [mmTV Remote](https://github.com/Chiuvenz/mmTVRemote).

## Adapters

| Adapter | Bundle ID | Upstream |
|---|---|---|
| **BiliTVMac** | `com.mmtv.bilitv` | [bili-webos](https://github.com/asdf17128/bili-webos) v2.5.1 |

## Layout

```text
Integrations/BiliTV/       # adapter boundary + manifest
Integrations/BiliTVMac/    # Electron macOS runtime
Scripts/                   # fetch / build / smoke
External/                  # gitignored upstream extract
```

## Build BiliTVMac

Requires Node.js, network (first run downloads Electron + upstream `.ipk`), and a graphical session for the default smoke test.

```sh
./Scripts/build-bilitv.sh
# optional: MMTV_SKIP_BILITV_SMOKE=1 ./Scripts/build-bilitv.sh
```

Output: `Integrations/BiliTVMac/dist/` and a copy under `dist/BiliTVMac-0.1.0-arm64.zip`.

Install the `.app` (e.g. into `/Applications`). mmTV’s video module detects `com.mmtv.bilitv` and launches with `--tv-fullscreen`.

## Launch contract (mmTV ↔ BiliTVMac)

- Bundle ID: `com.mmtv.bilitv`
- Launch args from mmTV: `--tv-fullscreen`
- Isolated Application Support state; no embedding in `com.mmtv.mac`
- HDMI living-room target remains 1080p unless the user asks otherwise

## Provenance

Migrated from [Chiuvenz/mmTV](https://github.com/Chiuvenz/mmTV) `Integrations/BiliTV*`, `Scripts/*-bilitv.sh` (history preserved via `git filter-repo`). Upstream BiliTV is MIT; see `Integrations/BiliTVMac/THIRD-PARTY-NOTICES.md`.
