# zsnapple
zfs snapshots

## Examples

### Daily recursive snapshot of tank, only keeping 365 snaps matching that pattern

```
zsnapple -f short -l 365 -p daily -r -v tank
```

### Hourly recursive snapshot of tank/smb, compatible with M$ shadowcopy, only keeping 24 matching that pattern

```
zsnapple -f shadow -l 24 -r -v tank/smb
```

use a crontab for glory
