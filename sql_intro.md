# SQL REFERENCE

## Create a TABLE

```sql
CREATE TABLE table_name (
    row_name_01 VARCHAR(50),
    row_name_02 INTEGER,
)
```

## Insert data

```sql
INSERT INTO table_name (row_name_01, row_name_01)
VALUES
    ('values_01', 'values_02'),
    ('values_11', 'values_12'),
    ('values_21', 'values_22');
```

## Retrieve data

### Get all the data from a table

```sql
SELECT * FROM table_name
```

### Get specific fields

```sql
SELECT value_01 FROM table_name
```
