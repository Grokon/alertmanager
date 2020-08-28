---
layout: default
title:  mysql_hres_alerts
categories: alerts
---



## mysqlslavestatus
- проверяем mysql slave status: ```show slave status \G```
- если видим ошибку вида ```Could not execute Update_rows event on table intelbet.football_lineup; Can't find record in 'football_lineup'``` или подобную, значит отсутствуют какие-то записи. И в данном случае можно просто пропустить этот запрос.
- останавливаем slave: ```stop slave;```
- пропускаем 1 запись: ```SET GLOBAL SQL_SLAVE_SKIP_COUNTER = 1;```
- запускаем slave: ```start slave;```
- проверяем slave статус, если все нормально, то нужно проверить еще раз.
- если ошибка остается, повторяем шаги.
- если данная проблема возникла после миграции или не хватает какго-то столбца, то нужно проверять миграции и порядок заливки.