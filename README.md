# zsnapple
zfs snapshots

## Examples

### Daily recursive snapshot of tank, only keeping 365 snaps matching that pattern

test

```
zsnapple -f short -l 365 -p daily -r -v tank
```

crontab at 3:30 am

```
PATH=/sbin:/bin:/usr/sbin:/usr/bin:/usr/local/sbin:/usr/local/bin:/root/bin
30 3 * * * zsnapple -f short -l 365 -p daily -r -v tank
```

### Hourly recursive snapshot of tank/smb, compatible with M$ shadowcopy, only keeping 24 matching that pattern

test

```
zsnapple -f shadow -l 24 -r -v tank/smb
```

crontab at every hour and 0 minutes

```
PATH=/sbin:/bin:/usr/sbin:/usr/bin:/usr/local/sbin:/usr/local/bin:/root/bin
0 * * * * zsnapple -f shadow -l 24 -r -v tank/smb
```
