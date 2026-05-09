# Thetis — PA3GHM TL2-1 fork

This repository is a **fork** of [ramdor/Thetis](https://github.com/ramdor/Thetis)
maintained by **PA3GHM (cjenschede)** as the companion build for the
[ThetisLink](https://github.com/cjenschede/ThetisLink) remote-control client.

The fork is actively maintained on branch [`thetislink-tl2`](https://github.com/cjenschede/Thetis/tree/thetislink-tl2).
For the upstream `master` branch (a verbatim mirror of ramdor's archived tree),
switch the branch selector to `master`.

## Latest release

**[`TL2-1`](https://github.com/cjenschede/Thetis/releases/tag/TL2-1)** — drop-in
`Thetis.exe` + `ReleaseNotes.txt`, base [`v2.10.3.15`](https://github.com/ramdor/Thetis/releases/tag/v2.10.3.15)
(2 May 2026, last release by ramdor / MW0LGE / Richard Samphire).

## What this fork adds

The fork adds TCI extensions used by ThetisLink, all gated behind the
**"ThetisLink extensions"** checkbox in `Setup > Network > IQ Stream`:

- `tci_caps_ex` — capability broadcast so clients auto-detect available extensions
- `auto_recenter_ex` — server-side CTUN recenter (no round-trip)
- `rx_filter_preset_ex` — per-RX filter preset push (F1..VAR2/NONE)
- `ddc_sample_rate_ex` — per-RX DDC sample rate, up to 1536 kHz (stock cap is 384 kHz)
- Diversity auto-null suite (Auto / Smart / Ultra) with live phase/gain circle broadcast
- Push-based state updates that ThetisLink subscribes to

Build identifies as **`PA3GHM TL2-1`** next to the upstream version string in the
title bar.

With the **"ThetisLink extensions"** checkbox **off**, the stock TCI extension
behaviour of upstream v2.10.3.15 is preserved (the fork still carries its own
build tag, release notes and About metadata).

## Installation

From the [`TL2-1`](https://github.com/cjenschede/Thetis/releases/tag/TL2-1)
release page:

1. Download `Thetis.exe` and `ReleaseNotes.txt`
2. Back up the originals in your existing Thetis installation folder (e.g. rename `Thetis.exe` to `Thetis-original.exe`)
3. Drop in the fork files (overwrite)
4. Start Thetis — verify the title bar shows `PA3GHM TL2-1`

All other files (DLLs, database, settings) remain unchanged. Revert by
restoring the backed-up originals.

## Upstream

Original Thetis project by Richard Samphire (MW0LGE), maintained from 2019
to 2 April 2026 when it was archived. The upstream releases (with full
per-version change logs) are at:

- Repository: <https://github.com/ramdor/Thetis>
- Releases (per-version change logs): <https://github.com/ramdor/Thetis/releases>
- Last upstream release: [v2.10.3.15](https://github.com/ramdor/Thetis/releases/tag/v2.10.3.15)

Thetis itself derives from PowerSDR (FlexRadio) via OpenHPSDR. The full
provenance chain is documented in [`ATTRIBUTION.md`](ATTRIBUTION.md); the
fork notice and licensing scope are in [`NOTICE.md`](NOTICE.md).

## License

Distributed under **GNU General Public License v2.0-or-later**, same as
upstream:

- [`LICENSE`](LICENSE) — canonical GPLv2 text
- [`LICENSE-DUAL-LICENSING`](LICENSE-DUAL-LICENSING) — Richard Samphire's
  reservation on his own original contributions; does not extend to fork
  modifications introduced here
- [`NOTICE.md`](NOTICE.md) — fork notice
- [`ATTRIBUTION.md`](ATTRIBUTION.md) — upstream lineage and contributor credits

All fork modifications are licensed under GPL-2.0-or-later with no
additional reservation.

## Source diff against upstream

Per-file SPDX headers and `[ThetisLink TL2-1] BEGIN/END` markers identify
fork-modified sections. The cumulative diff against the upstream base tag is:

```bash
git diff v2.10.3.15..thetislink-tl2 --stat
git log v2.10.3.15..thetislink-tl2 --oneline
```

## Companion application

This fork is the companion build for **ThetisLink v2.0.0** — a remote-control
Rust application for ANAN 7000DLE + Thetis SDR over the network with audio,
spectrum, PTT and full radio control via TCI WebSocket.

Repo: <https://github.com/cjenschede/ThetisLink>

73 de PA3GHM
