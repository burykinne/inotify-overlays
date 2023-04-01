# Overview

This simple service is needed for check changes in all podman overlays
Service sends warning message to syslog, if some file/directory
were create,delete,modify or move in podman overlay.

# Install

Put `inotify-overlays` script to `/usr/bin` and `inotify-overlays.service` to
`/etc/systemd/systemd/`

Run
```
# systemd daemon-reload
# systemd enable --now inotify-overlays
```

Example message in system journal
```
Apr 01 21:30:47 host-20 podsec[11403]: WARNING File media was MOVED_TO,ISDIR in /home/podman_dev/.local/share/containers/storage/overlay/637c6038ca30676aa83440c6aba9c6318832f29ebd78f5282c8322e504f5a8da/diff/
```

