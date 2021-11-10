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

### Get specific fields with operations

```sql
SELECT value_01, value_02 * value_01 AS attribute_name From table_name
```

### Get specific fields with string operations

```sql
SELECT value_01, value_02 * value_01 || '$' AS attribute_name From table_name
```

> The [ **||** ] operator used to Join two strings

#### String Fucntions

> - CONCAT(`value_01`, `string or text`, `value_02`) <br/>
> - UPPER(`value_01`)
>   , LOWER(`value_01`)
>   <br/>
> - LENGTH(`value_01`)

## Filters

```sql
SELECT value_01, value_02 FROM table_name WHERE value_02 > some_v alue
```

## Update

```sql
UPDATE table_name SET row_name_01 = value_001 WHERE row_name_02 = value_02
```

## Delete

```sql
DELETE FROM table_name WHERE row_name_01 = values_01
```
