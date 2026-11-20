# Install

## Requirements

- macOS 27 or later, Apple silicon.
- Nothing else. Port Dashboard is free and needs no licence key or account.

## Install

1. Download `PortDashboard-1.0.0.dmg` from the [latest release](https://github.com/zyvorai/port-dashboard/releases/latest).
2. Optional: verify the download. In Terminal, from the folder that holds the DMG:

   ```sh
   shasum -a 256 -c PortDashboard-1.0.0.dmg.sha256
   ```

   It should print `PortDashboard-1.0.0.dmg: OK`. The expected SHA-256 is also in the release notes.
3. Open the DMG and drag **Port Dashboard** to **Applications**.
4. Open it from Applications. It has no Dock icon; look for its icon in the menu bar and click it.

The download is signed with a Developer ID certificate and notarized by Apple, so macOS opens it without a Gatekeeper warning. You can check that yourself:

```sh
spctl -a -t open --context context:primary-signature -v PortDashboard-1.0.0.dmg
xcrun stapler validate PortDashboard-1.0.0.dmg
```

## Launch at login

Settings (gear icon in the popover) > **Launch at login**. macOS may ask you to approve it in System Settings > General > Login Items.

## Uninstall

See [UNINSTALL.md](UNINSTALL.md).
