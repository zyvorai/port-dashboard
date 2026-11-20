# Privacy

**Port Dashboard does not collect, store or send any data.**

- **No network.** The app contains no network code, and it is signed with no entitlements. Opening a port in your browser hands a `localhost` URL to your browser; the app itself makes no connection.
- **No accounts, no analytics, no telemetry, no crash reporting.**
- **What it reads.** Process names, pids, working directories, memory and listening sockets, through `libproc`, only for the ports it displays, only in memory, and only while it runs. The app does not write any data files.
- **What it changes.** Only the processes you explicitly stop (see [HOW-IT-WORKS.md](HOW-IT-WORKS.md)).
- **Copy Diagnostics.** In Settings and About, this copies the app version, macOS version and CPU architecture to your clipboard. It never includes ports, process names or paths. It is not sent anywhere.
- **Launch at login.** If you turn it on, macOS stores the login item; that is a system setting you can remove in System Settings > General > Login Items.

This documentation website and repository are hosted on GitHub, which has its own privacy practices.
