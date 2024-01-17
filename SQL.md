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
3. Pg restore using verbose (.sql file)
  ```
  pg_restore --verbose --clean --no-acl --no-owner --host=localhost --dbname=db_name --username=username latest.sql
  ```
4. Pg restore (.dump file)
  ```
  pg_restore -d bella_oman -p 5437 bella_live_2024-01-11_10-44-15.dump -U sltech
  ```

