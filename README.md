# Automatic F5 backups 

This will define sites and definition of F5 configuration backups.

1. Backup both active and standby at every sites where we have F5
    * (TODO) Need to provide central location for this
2. Backup once a week
    * midnight at Friday (So friday night going into sat)
    * File format : $(hostname)-hhmm-mmddyy.ucs

## cli command to backup
```
tmsh save sys ucs $(echo $HOSTNAME | cut -d'.' -f1)-$(date +%H%M-%m%d%y)
```

### how to restore from backup (however, this is not applicable for this project)
```
tmsh load /sys ucs <path/to/UCS> no-license
```
___
Ref
https://support.f5.com/csp/article/K13132
