# Cloud9 JetStream for lich

## Overview

A dark theme for [lich](https://github.com/omartelo/lich) built for long coding
sessions: deep navy-black backgrounds, restrained Cloud9-blue accents, and a
palette that stays out of your way.

This is a port of [Cloud9 JetStream](https://plugins.jetbrains.com/plugin/31876-cloud9-jetstream)
by [Cloud9 Esports Inc.](https://github.com/cloud9esports), the JetBrains IDE
theme ([source](https://github.com/cloud9esports/cloud9-theme)). Upstream ships a
single dark variant, so this pack does too.

## Variants

| Theme | `id` | `scheme` |
|---|---|---|
| Cloud9 JetStream | `cloud9-jetstream` | dark |

## Installation

lich installs a theme repository from its URL — nothing to download or copy by
hand:

1. Open lich and go to **Settings → Appearance**.
2. Next to **Theme**, click **Import**.
3. Paste `https://github.com/lichdotdev/cloud9-jetstream-lich` and click **Install**.
4. Pick **Cloud9 JetStream** in the theme picker. The terminal picker defaults to
   **Match app theme**, so one pick dresses the interface and the terminal panes
   alike.

Later releases are taken with **Update** on the theme's row.

### Local install

An absolute path is an accepted remote, so a clone installs the same way:

```bash
git clone https://github.com/lichdotdev/cloud9-jetstream-lich.git
```

Then paste the absolute path of the clone into **Settings → Appearance → Import**.

## How the palette maps

The app tokens take the colors upstream uses for the same roles in
[`cloud9theme.theme.json`](https://github.com/cloud9esports/cloud9-theme/blob/main/resources/theme/cloud9theme.theme.json).

| Role | Color | Upstream |
|---|---|---|
| `background` / `foreground` | `#0a0e14` / `#d4e4f7` | `*.background` / `*.foreground` |
| `card` | `#060a10` | `EditorTabs`, `MainToolbar`, `StatusBar` |
| `popover` | `#111820` | `Popup.background` |
| `sidebar` | `#0e141e` | `ToolWindow.background` |
| `accent` | `#1f3247` | `selectionBackground` |
| `secondary` | `#151d27` | `Button.startBackground` |
| `primary` | `#0077b6` | `Button.default.startBackground` |
| `ring` | `#3d9bc9` | `focusedBorderColor` |
| `border` / `input` | `#1a2332` / `#1f3247` | `borderColor` / `Popup.borderColor` |
| `muted-foreground` | `#8899aa` | `infoForeground` |
| `destructive` | `#ff6b6b` | `errorForeground` |
| `tone-pass` / `tone-wait` | `#57cc99` / `#e2b55a` | `Banner.success*` / `warningForeground` |

The terminal palette is the `CONSOLE_*_OUTPUT` colors of upstream's editor
scheme [`cloud9-scheme.xml`](https://github.com/cloud9esports/cloud9-theme/blob/main/resources/theme/cloud9-scheme.xml),
with caret (`#00d4ff`) and selection (`#0d3a58`) from the same file. One
deviation: upstream's ANSI black is the editor background itself, which makes
black-on-default text invisible, so `black` is `#1e293b`, the top background
tier of the palette.

## Thanks to

- [Cloud9 Esports Inc.](https://github.com/cloud9esports) — Cloud9 JetStream,
  the original palette and [cloud9-theme](https://github.com/cloud9esports/cloud9-theme).
- [omartelo](https://github.com/omartelo) — lich port

## Contributing

The theme is one lich theme file — `cloud9-jetstream.json` — beside the
`lich-theme.json` manifest that carries the pack's version. There is no
generator: colors are edited directly in the theme file.

1. Fork the repo.
2. Edit `cloud9-jetstream.json`.
3. Validate the **whole directory** — a repository installs all or nothing:
   `node validate.mjs .` (ships with the lich `theme` skill).
4. Bump `version` in `lich-theme.json` in the same commit. An unbumped version
   ships nothing: **Update** compares only that number.
5. Open a PR.

## License

[BSD-3-Clause](./LICENSE), the same as [cloud9-theme](https://github.com/cloud9esports/cloud9-theme).
Cloud9 is a trademark of Cloud9 Esports Inc.; this port is not affiliated with
or endorsed by them.
