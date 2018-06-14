# unifi-troubleshooting

UniFi Controller and UniFi-Video on same whitebox server.

# UniFi Controller wouldn't start

Recently received an rc=1 error in my /usr/lib/unifi/logs/server.log.  The UniFi service would start but the database would immediately die.
This happened after i did my standard upgrade process:
```
sudo apt-get update && sudo apt-get upgrade --y && sudo apt-get autoremove -y && sudo shutdown -r now
```
When the box came back online, the UniFi website wouldn't come up.  Investigating the log, i discovered the mongodb wasn't running.

Ultimately i had to run the following to force a reinstall which fixed the issue.
```
sudo apt-get install unifi --reinstall
```

