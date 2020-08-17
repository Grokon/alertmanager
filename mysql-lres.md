---
layout: default
title:  mysql_lres_alerts
categories: alerts
---



## MYSQLGroupReplication
- Check logs, check server status:
```shell
select * from performance_schema.replication_group_members;
show variables like '%read_only';
select * from performance_schema.replication_connection_status\G
```
- Try to restart replications:
```start GROUP_REPLICATION;```
and check status agayne.

