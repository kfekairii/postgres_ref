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

# Joins and Aggregation

## 1. Joins

- produces values by merging together rows from diffrent related tables.
- used to find data that involves multiple resources.

### Inner Join

```sql
SELECT url, username FROM photos
JOIN users on users.id = photos.user_id
```

If there is no match, the photo will be droped from the result.

### Left Join

```sql
SELECT url, username FROM photos
LEFT JOIN users on users.id = photos.user_id
```

Will keep photos with unmatched users.

### Right Join

```sql
SELECT url, username FROM photos
RIGHT JOIN users on users.id = photos.user_id
```

will include all users even if the don't have a photo.

### Three way join

```sql
SELECT
	comments.id AS comment_id,
	username,
	contents,
	url,
	photos.user_id,
	comments.user_id
FROM comments
JOIN photos ON photos.id = comments.photo_id
JOIN users ON comments.user_id = users.id AND users.id = photos.user_id
```

## 2. Grouping

- Reduces many rows down to fewer rows.
- Done with '`GROUP BY`' key word.

```sql
SELECT user_id, COUNT(id) FROM comments
GROUP BY user_id
```

## 3. Aggregation

- Looks at many rows and calculates a single value
