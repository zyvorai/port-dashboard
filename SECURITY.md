# Security

Port Dashboard has no network code and no entitlements, and reads process information through libproc. The only action that changes anything is stopping a process you select, which is limited to your own processes (see [docs/HOW-IT-WORKS.md](docs/HOW-IT-WORKS.md)).

To report a vulnerability, use GitHub's private vulnerability reporting on this repository (Security tab > Report a vulnerability). Please do not put exploit details in a public issue.
