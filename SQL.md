1. If else statement in update query
```
UPDATE product_template SET tracking = CASE WHEN detailed_type = 'product' THEN 'lot' ELSE 'none' END;
```

2. To see statics in postgress sql visit
```
https://www.postgresql.org/docs/current/monitoring-stats.html#MONITORING-PG-STAT-ACTIVITY-VIEW
```
