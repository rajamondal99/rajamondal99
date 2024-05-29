1. If else statement in update query
```
UPDATE product_template SET tracking = CASE WHEN detailed_type = 'product' THEN 'lot' ELSE 'none' END;
```

2. To see statics in postgress sql visit
```
https://www.postgresql.org/docs/current/monitoring-stats.html#MONITORING-PG-STAT-ACTIVITY-VIEW
```
  >>First set some parameters 
  ```
  https://www.postgresql.org/docs/current/sql-set.html
  ```
3. Pg restore using verbose (it works with both the file type .sql/.dump file)
  ```
  pg_restore --verbose --clean --no-acl --no-owner --host=localhost --dbname=db_name --username=username latest.sql
  ```
4. Pg restore (.dump file)
  ```
  pg_restore -d bella_oman -p 5437 bella_live_2024-01-11_10-44-15.dump -U sltech
  ```
5. Gunzip. Restore database from dump.sql.gz file.
   ```
   gunzip < dump.sql.gz | sudo -u sltech psql bella_13 -p 5437
   ```

6. Curl Command.
```
curl -X POST -F 'master_pwd=NWVSNx6tLOStkaMr' -F 'name=moonshine_live' -F 'backup_format=zip' -o /opt/moonshine_live_01_april_2024.zip http://localhost:8069/web/database/backup
```


7. How to check index of any table in postgres?
   ```
   SELECT 
    indexname,
    indexdef
    FROM
        pg_indexes
    WHERE
        tablename = 'your_table_name';

   ```
