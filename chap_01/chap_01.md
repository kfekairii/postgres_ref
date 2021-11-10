# Relationships

## One-to-Many

> A user has many photos

## Many-to-One

> Many photos has one user

## One-to-One

> A Capitol has one Country

## Many-to-Many

**Students** has many **Classes** <br/>
Many **Classes** has many **Students**

# Example

### 1. Create a **users** Table

```sql
CREATE TABLE users(
    id SERIAL PRIMARY KEY,
    username VARCHAR(50)
);
```

### 2. add user

```sql
INSERT INTO users (username)
VALUES
    ('kfeka'),
    ('kfekairi'),
    ('user_101');
```

### 3. Create **photos** table

```sql
CREATE TABLE photos(
    id SERIAL PRIMARY KEY,
    url VARCHAR(200),
    user_id INTEGER REFERENCES users(id)
);
```

### 4. Insert photos data

```sql
insert into photos(url,user_id)
values
     ('some.url/ifd.jpg',1),
 	('some.url/ifd02.jpg',2),
	('some.url/ifd03.jpg',3);
```

### 5. find photos by user_id

```sql
Select * from photos
where user_id=3
```

### 6. Join two tables data

```sql
SELECT url, username FROM photos
JOIN users on users.id = photos.user_id
```
