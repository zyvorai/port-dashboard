# Uninstall

1. Quit Port Dashboard: click its menu-bar icon, then the power button (or press Command-Q).
2. If you enabled **Launch at login**, turn it off first in Settings, or remove it in System Settings > General > Login Items.
3. Drag **Port Dashboard** from Applications to the Trash.

Optional clean-up of the small preferences file macOS may have created:

```sh
defaults delete dev.zyvor.ports 2>/dev/null
rm -f ~/Library/Preferences/dev.zyvor.ports.plist
```

Port Dashboard installs no helper, daemon, kernel extension or other files, and stores no data of its own.
