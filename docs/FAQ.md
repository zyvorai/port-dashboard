# FAQ

**Do I need a licence?** Port Dashboard is proprietary software. See [LICENSE](../LICENSE) for the terms (no redistribution or reverse engineering).

**Which macOS?** macOS 27 or later, Apple silicon.

**Does it use the network?** No. There is no network code and no entitlements. See [PRIVACY.md](PRIVACY.md).

**Why do I not see a service I know is running?** Without administrator rights macOS exposes only this account's sockets. Services run by other users (for example some system daemons) are not listed. Only listening TCP and bound, unconnected UDP sockets are shown.

**Why is Stop greyed out for a row?** Hover the button: it says why. Rows owned by another user, system processes and Port Dashboard itself cannot be stopped.

**What is the difference between Stop and Force Kill?** Stop sends SIGTERM, which lets the process shut down cleanly. Force Kill sends SIGKILL, which ends it immediately; unsaved work is lost. Force Kill is only offered if the process is still running after Stop, and needs a second confirmation.

**What does "All interfaces" mean?** The process is listening on the wildcard address, so other devices on your network can try to connect (subject to your firewall). "This Mac only" means loopback. "One interface" means one specific address.

**Why does a row say "No project folder"?** The process's working directory is not inside a git repository, or macOS did not let the app read it.

**Are the screenshots real?** They are rendered from the app's own views with invented sample rows, not captured from a running session. Captions say "Sample data".

**Is the source available?** No. This repository holds documentation and release downloads only.

**macOS says the app is damaged or from an unidentified developer.** Re-download the DMG and verify the checksum (see [INSTALL.md](INSTALL.md)). The build is notarized, so a normal download opens without a warning. If it still does, please open an issue with your macOS version.
