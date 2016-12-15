# Command

dump from shengupiao and then restore into shengupiao1 ()

```
pg_dump -h 127.0.0.1 -t stock -U shengupiao shengupiao  | psql -h 127.0.0.1 -U shengupiao shengupiao1
```

dump and restore separately (data only) -a

```
pg_dump -h 127.0.0.1 -t investors -a -U shengupiao shengupiao > investors
psql -h rdsd3u3px3pp86bw2a43.pg.rds.aliyuncs.com -p 3433 -U shengupiao shengupiao < investors
```

pg_restore can also be used

import a csv

```
CREATE TABLE local_management (
  id SERIAL PRIMARY KEY,
  product_name TEXT,
  type TEXT,
  reference_code TEXT,
  reference_date TEXT,
  management_type TEXT,
  manager TEXT,
  found_date TEXT,
  investment_manager TEXT,
  investment_consultant TEXT,
  investment_scope TEXT,
  expected_annual_earning TEXT,
  duration TEXT,
  closed_peroid TEXT,
  raise_amount FLOAT,	
  maturity_date TEXT,
  promotion_start_date TEXT,
  promotion_end_date TEXT,	
  investment_threshold TEXT,
  custodian TEXT
);

\COPY local_management FROM '/home/ouyexie/Workspace/management.csv' DELIMITER ',' CSV;
```

# Reference

 - http://www.postgresql.org/docs/9.4/interactive/backup-dump.html
 - [CSV文件如何导入数据到一个Postgres表？](http://qa.helplib.com/121172)
 - [How to import CSV file data into a PostgreSQL table?](http://stackoverflow.com/questions/2987433/how-to-import-csv-file-data-into-a-postgresql-table)
 - [postgresql导出sql执行结果到文件的方法](http://blog.sina.com.cn/s/blog_840dd283010178jz.html)
 - [PgSql备份pg_dump与还原手记pg_restore（转）](http://rainbow702.iteye.com/blog/1318741)