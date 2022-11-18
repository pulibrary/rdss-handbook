# Open Publishing, a.k.a. OJS

We run open journal system (OJS) at openpublishing.princeton.edu

Backups happen via a cron job, nightly. For an OJS backup, you need:

1. An export of the database
2. A snapshot of the uploaded files

This backup happens nightly. In princeton_ansible, see `roles/ojs/tasks/automate_backups.yml` for exact details.

To restore from a backup:

1. Copy the backup you want from /var/local/ojs_backups to the system where you want to restore
2. Shut down apache: `sudo service apache2 stop`
3. Restore the database:

```
pg_restore --verbose --clean --no-acl --no-owner --host localhost -U USERNAME --dbname my-destination-database /path/to/sqlfile.dump
```

4. Copy the files directory to /var/local/files and ensure it is owned by deploy:www-data
5. Restart apache: `sudo service apache2 start`
