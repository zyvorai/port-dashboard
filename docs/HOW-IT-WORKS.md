# How it works

## What it lists

Every few seconds (three) Port Dashboard walks the processes this account can see through `libproc` and reads their sockets:

- **TCP** sockets in the LISTEN state.
- **UDP** sockets that are bound and not connected.

IPv4 and IPv6 sockets of one process on the same port are merged into one row. Each row shows:

| | |
| --- | --- |
| Port and protocol | for example `3000 TCP` |
| Process and pid | the name the system reports |
| Project | the process's working directory, walked up to the nearest folder containing `.git`; its name is shown |
| Memory | physical footprint, the number Activity Monitor calls Memory |
| Scope | **This Mac only** (loopback), **All interfaces** (wildcard bind) or **One interface** |

Because it runs without administrator rights, the system only exposes this account's sockets. Services run by other users are not listed.

## Filtering

The text field matches port number, process name or project name. The segmented control shows All, TCP, UDP, or **Exposed** (anything not bound to loopback only).

Keyboard: Command-R refresh, Command-F focus the filter, Escape clear it, Command-I About, Command-Q quit.

## Open and copy

For TCP ports **Open** opens `http://localhost:<port>` in your default browser (`https` for 443 and 8443; a port bound to one specific address uses that address). **Copy URL** copies the same URL. UDP ports have no URL.

## How Stop works

1. Press the stop button on a row. An inline confirmation asks `Stop <process> (pid <n>)?`.
2. On **Stop**, the app sends `SIGTERM` (a polite request to quit) and watches the process for about three seconds.
3. If it exits, the row disappears on the next refresh.
4. If it is still running, the row says so and offers **Force Kill**. That needs a second confirmation and sends `SIGKILL`. Unsaved work in that process is lost.

### The guard

A stop is refused, and the button is disabled with the reason, when:

- the process is owned by another user,
- it is a system process (pid 0 or 1),
- it is Port Dashboard itself,
- or Port Dashboard is running as root.

Before any signal is sent the app re-reads the process and checks that the pid still has the same owner and start time as the row you confirmed. If the pid has been reused by a different process, nothing is signalled.

## What it does not do

- No network access, no account, no analytics. See [PRIVACY.md](PRIVACY.md).
- It does not change firewall rules, bind addresses or any setting. The only change it can make is stopping a process you chose.
- It does not list another user's services, and it does not show traffic.

## Quality

The app ships with automated self-tests (scanner, kill guard, filters and helpers) that run headless. The kill guard test stops real child processes: one that exits on SIGTERM and one that ignores it and needs SIGKILL. The interface has not yet been clicked through by a human on a clean Mac.
