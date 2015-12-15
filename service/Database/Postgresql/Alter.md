# ALTER a COLUMN

<pre>
<code>
ALTER TABLE [ ONLY ] name [ * ]
    action [, ... ]
ALTER TABLE [ ONLY ] name [ * ]
    RENAME [ COLUMN ] column TO new_column
ALTER TABLE name
    RENAME TO new_name
ALTER TABLE name
    SET SCHEMA new_schema

这里 action 是下列之一：

    ADD [ COLUMN ] column type [ column_constraint [ ... ] ]
    DROP [ COLUMN ] column [ RESTRICT | CASCADE ]
    ALTER [ COLUMN ] column TYPE type [ USING expression ]
    ALTER [ COLUMN ] column SET DEFAULT expression
    ALTER [ COLUMN ] column DROP DEFAULT
    ALTER [ COLUMN ] column { SET | DROP } NOT NULL
    ALTER [ COLUMN ] column SET STATISTICS integer
    ALTER [ COLUMN ] column SET STORAGE { PLAIN | EXTERNAL | EXTENDED | MAIN }
    ADD table_constraint
    DROP CONSTRAINT constraint_name [ RESTRICT | CASCADE ]
    DISABLE TRIGGER [ trigger_name | ALL | USER ]
    ENABLE TRIGGER [ trigger_name | ALL | USER ]
    CLUSTER ON index_name
    SET WITHOUT CLUSTER
    SET WITHOUT OIDS
    OWNER TO new_owner
    SET TABLESPACE new_tablespace
</code>
</pre>

# Drop not null

```
lter table financial_reports alter column industry drop not null;
```

# Rename

```
ALTER INDEX SCno RENAME TO SCSno;
```

```
alter table TABLE_01 rename to TABLE_10;
```

# Reference

 - http://blog.chinaunix.net/uid-15145533-id-2775847.html
 - http://bbs.csdn.net/topics/391024303
 - http://www.ehow.com/how_6109781_change-table-name-sql.html