# Changelog

## 1.0.0

First public release of Port Dashboard, a free macOS menu-bar app.

- Lists listening TCP ports and bound UDP ports with process, pid, project folder (working directory up to the git root), memory and scope (This Mac only, All interfaces, One interface). Refreshes every three seconds.
- Filter by text (port, process, project) and by All, TCP, UDP or Exposed.
- Open a TCP port in the browser, copy its URL.
- Stop a process: confirmation, SIGTERM, then a second confirmation before Force Kill (SIGKILL). Own-user processes only; never pid 0 or 1, never itself, never as root; pid identity re-checked by start time.
- Liquid Glass popover for macOS 27, light and dark, keyboard shortcuts, VoiceOver labels, Reduce Motion and Reduce Transparency respected, About window, launch at login.
- No network access, no entitlements. Developer ID signed and notarized.
- Requires macOS 27 or later on Apple silicon.
