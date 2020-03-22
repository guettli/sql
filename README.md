# Thoughts and ideas about SQL

## Intro

[SQL (Wikipedia)](https://en.wikipedia.org/wiki/SQL): 

> SQL Structured Query Language) is a domain-specific language used in programming and designed for managing data held in a 
> relational database management system (RDBMS).

## Sub Select: shortcut for table name

Select all products which belong to a category which has expired:

```
SELECT id, name
FROM products
WHERE category_id IN
   (SELECT id
    FROM ...
    WHERE expired = True)
```

Up to now you need to specify the category table after the FROM. It would be very handy, if
you could omit it by using a special syntax (here `...`), if `category_id` is a Foreign-Key to the category-table.
This would be very hand and would reduce the likelihood of typos while writing SQL.


    
