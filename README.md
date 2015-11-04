# zsnapple
zfs snapshots

## Examples

### Daily recursive snapshot of tank, only keeping 365 snaps matching that pattern

test

```
           zsnapple -f short -l 365 -r -v tank -p daily
```

crontab at 3:30am daily

```
PATH=/sbin:/bin:/usr/sbin:/usr/bin:/usr/local/sbin:/usr/local/bin:/root/bin
30 3 * * * zsnapple -f short -l 365 -r -v tank -p daily -q
```

### Hourly recursive snapshot of tank/smb, compatible with M$ shadowcopy, only keeping 24 matching that pattern

test

```
          zsnapple -f shadow -l 24 -r -v tank/smb -p hourly
```

crontab at 0 minutes hourly

```
PATH=/sbin:/bin:/usr/sbin:/usr/bin:/usr/local/sbin:/usr/local/bin:/root/bin
0 * * * * zsnapple -f shadow -l 24 -r -v tank/smb -p hourly -q
```

### Prune dailies by date, not just by count

```
          zsnaprune -f short -l 120 -v tank/urep/backup -q
```
