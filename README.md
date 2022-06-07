# scrubctl
scrubctl can be used to control scrub on ZFS pools. zpool scrub does not make
a difference between starting a new scrub and resuming a paused scrub.
`scrubctl resume` will start the scrub **only** if it is paused. It is therefore
safe to put scrubctl pause/resume e.g. to cron, as it will not start a new
scrub.

## Usage
```
Usage: scrubctl start|resume|pause|stop pool...
    -n, --dry-run                    Only print what would happen
    -q, --quiet                      Print only fatal errors
    -h, --help                       Show this message

Commands:
  start        Initiate zpool scrub
  stop         Stop zpool scrub
  resume       Resume zpool scrub if it is currently paused
  pause        Pause zpool scrub
```
