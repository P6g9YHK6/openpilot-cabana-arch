# openpilot-cabana-arch

Arch Linux packaging for [Cabana](https://github.com/commaai/openpilot/tree/master/openpilot/tools/cabana), the CAN bus visualizer and DBC editor from comma.ai openpilot. This repository holds the packaging only; the source is fetched from `commaai/openpilot` at a pinned commit.

Published to the AUR as [`openpilot-cabana`](https://aur.archlinux.org/packages/openpilot-cabana):

```bash
yay -S openpilot-cabana
```

## Layout

- `aur/`: the AUR package files, published as-is.
- `.github/workflows/check-upstream.yml`: checks hourly for commits touching `openpilot/tools/cabana` and bumps the pin.
- `.github/workflows/sync-aur.yml`: builds the package, then publishes `aur/` to the AUR if the build succeeds.
- `.github/workflows/verify-aur-commit.yml`: confirms the AUR matches this repository after a sync.

## Earlier versions

Before version 2.0 this package built the standalone Qt app from [`deanlee/openpilot-cabana`](https://github.com/deanlee/openpilot-cabana). That packaging is preserved on the `backup/main-deanlee` branch.
