---
layout: default
title:  mysql_lres_alerts
categories: alerts
---



## MYSQLGroupReplication
- Check logs, check server status:
```shell
select * from performance_schema.replication_group_members;
```
You can see this: 
```shell
+---------------------------+--------------------------------------+----------------+-------------+--------------+-------------+----------------+
| CHANNEL_NAME              | MEMBER_ID                            | MEMBER_HOST    | MEMBER_PORT | MEMBER_STATE | MEMBER_ROLE | MEMBER_VERSION |
+---------------------------+--------------------------------------+----------------+-------------+--------------+-------------+----------------+
| group_replication_applier | 08b18a86-aeab-11e9-98de-629d21d14bb0 | 10.135.185.198 |        3306 | ONLINE       | PRIMARY     | 8.0.20         |
| group_replication_applier | 1ea56238-639d-11ea-a8b1-ba94ca3fba11 | 10.135.102.241 |        3306 | ONLINE       | PRIMARY     | 8.0.19         |
| group_replication_applier | b5300b93-b1b6-11e9-812b-cae31306b76e | 10.135.252.152 |        3306 | ONLINE       | PRIMARY     | 8.0.19         |
+---------------------------+--------------------------------------+----------------+-------------+--------------+-------------+----------------+

```
Если вы видите ошибку (ERROR), на текущий статус - то нужно перезапустить групповую репликацию:
```stop GROUP_REPLICATION;```
```start GROUP_REPLICATION;```

## MYSQLREADONLY
- Проверяем статус репликации (смотри MYSQLGroupReplication)
- Далее проверяем значение переменной:
```bash
show variables like '%read_only';
```
Должно показать:
```bash
+-----------------------+-------+
| Variable_name         | Value |
+-----------------------+-------+
| innodb_read_only      | OFF   |
| read_only             | ON    |
| super_read_only       | ON    |
| transaction_read_only | OFF   |
+-----------------------+-------+
```
Если все значение OFF, значит все нормально.

- Посмотреть статус по транзациям:
```select CHANNEL_NAME,SERVICE_STATE from performance_schema.replication_connection_status;```
Должно быть:
```bash
+----------------------------+---------------+
| CHANNEL_NAME               | SERVICE_STATE |
+----------------------------+---------------+
| group_replication_applier  | ON            |
| group_replication_recovery | OFF           |
+----------------------------+---------------+
```
Если значения наоборот, то необходимо дождаться восстановления репликации и посмотреть все значения (*) на наличие ошибок.

- Если все прерыдущие пункты показывает нормально, то можно поменять значение системной переменной:
```SET GLOBAL read_only=0;```
после этого так же проверяем все статусы и значение этой переменной. 

- Так же посмотреть по расходу памяти:
```free -m```
если свободной памяти почти не осталось, то перезашоузить mysql и проверить все пункты заново:
```systemctl restart mysql```
