
Backup Scripts
==============

 * pg_backup.config - The main configuration file. This should be the only file which needs user modifications.
 * pg_backup.sh - The normal backup script which will go through each database and save a gzipped and/or a custom format copy of the backup into a date-based directory.
 * pg_backup_rotated.sh - The same as above except it will delete expired backups based on the configuration.

Cron
====

crontab -e

5 0 * * * /path/to/command ::



      * * * * * command to be executed
      - - - - -
      | | | | |
      | | | | ----- Day of week (0 - 7) (Sunday=0 or 7)
      | | | ------- Month (1 - 12)
      | | --------- Day of month (1 - 31)
      | ----------- Hour (0 - 23)
      ------------- Minute (0 - 59


Restore
=======

pg_restore --list archive.backup

createdb --port 54321 mons1

pg_restore --dbname=mons1 --port 54321 --username=postgres archive.backup

Further Readings and links
==========================

https://www.postgresql.org/docs/current/static/app-pgdump.html
https://www.postgresql.org/docs/current/static/app-pgrestore.html

https://www.postgresql.org/docs/current/static/continuous-archiving.html
https://www.postgresql.org/docs/current/static/high-availability.html
