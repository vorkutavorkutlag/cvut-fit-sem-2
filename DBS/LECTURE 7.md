
You will need some application to execute SQL queries.
A reliable choice is PostgreSQL.
It supports SQL queries, such as `SELECT * FROM hotels;`
Then backslash `d` something is another command, usually for dumping.
For example, dump table `\dt`.

```sql
SELECT [specification of columns]
FROM [specification of source]
WHERE [condition of selection]
ORDER BY [specification of sorting]
```
The last two are optional.

specification of columns = `{DISTINCT, ALL}`

According to the standard, the shortest query is `SELECT * FROM table;`
However, different implementations, like PostgreSQL, don't entirely abide by the standard. For example, `SELECT 5*5` will return `25`.
`SELECT * FROM *` is a syntax error. `SELECT *` is redundant...

The SQL query `SELECT director, year FROM Movie;` and RA query `Movie[director, year]` are not the same, seeing as we operate on sets in RA as opposed to SQL.

However, we can use the `DISTINCT` keyword to show unique items only without any duplicates.

DISTINCT is always applied to the whole statement SELECT.
Sorting by using DISTINCT is usually implicit (but it does not necessarily have to be).

When defining the order in `ORDER BY`, we can define ascending/descending with:
`SELECT director, year FROM Movie ORDER BY director DESC, year ASC;`
The ascending is the default, but we can be explicit without any change.

An example of a condition: `SELECT * FROM Movie WHERE year < 1940`
We can use logical operators in the where class. Boolean operators `=, != or <>, <, >, <=, >=` and we also have BETWEEN. For example, Instead of:
`SELECT * FROM Movie WHERE year >= 1938 AND year <= 1940` it is possible to write:
`SELECT * FROM Movie WHERE year BETWEEN 1938 AND 1940`.

This is because SQL is wrapped to be written like a spoken language, and then the meaning is interpreted in the inner logic.
Though, that little detail is not that important, and an argument could be made that not using the `BETWEEN` keyboard is more readable.

A form of query we should avoid: `SELECT * FROM Movie WHERE year < 1940 OR year < 1950 AND year > 2000`
NOT has highest priority, then AND, then OR.
In reality, the query looks like this: `SELECT * FROM Movie WHERE year < 1940 OR (year < 1950 AND year > 2000)`
This is priority of operands.
In general it is a good habit of using parenthesis when to be explicit with our logic.

The condition can be either true or false for the row. It is returned or not returned respectively. It is also possible for the condition to be null, which is weird, but still won't be returned, so no need to worry, I suppose?

How does logic work when bool values are null?
It is not equivalent to a value of zero or empty string, it is a distinct value all the data types have.
![[Pasted image 20260330104325.png]]


Null is essentially equivalent to 'We don't know', and the rest of the logic follows suit.
Another example being, `SELECT 42 < NULL` is `NULL`.
If we are not sure how a condition will behave exactly, the simplest way is to try it out like this without fetching real data.

We can concatenate strings with the double pipe operator.
Concatenating a string with null is null. Otherwise, the join condition works as expected. However, if we run these queries in Oracle, then null would be interpreted as an empty string.

It is best to run queries that avoid null explicitly by checking if it is null.
Mainly, by using `IS NULL` and `IS NOT NULL` keywords.
`COALESCE` is a function that returns the first argument that's not null.
For example, `SELECT COALESCE(NULL, NULL, 123, 42);` will return 123.

After `JOIN`, it is possible to join tables together. 
These include `JOIN ON`, `JOIN USING`, `NATURAL JOIN`, `CROSS JOIN`, equivalent w/ `,` .
Examples include:
![[Pasted image 20260330105538.png]]

Cartesian with conditions will result in the same as the other fancy joins.

// You can comment out queries with `--` in the beginning of the line.

`JOIN ... USING` is really nice...!
Check slides for more examples.

We can use `AS` to rename tables. This is silly, but maybe a little useful when joining tables with themselves. (?)
In RA, opposed to this, we can only rename columns.

The server optimizes the queries, seeing how the result would look like, and only then building a new query on its own to inquire it.

It is possible to use arithmetic expressions in the select statement.
For example, 
`SELECT name, salary/25.41 AS "euroSalary" FROM Employee WHERE birth_number IS NULL`

We can use the `COALESCE` function to supplement the nulls with zeros, for example.
`SELECT name, (COALESCE(salary, 0))/25.41 AS "euroSalary" FROM Employee WHERE birth_number IS NULL`

When we develop applications, we don't necessarily use SQL, we use the framework around it, then we use the application and learn it.
Some databases are not analyzed by these frameworks, and we want to analyze them more pedantically. These queries can happen to be more complex.
Mainly for research purposes.

We can limit the number of queries. `LIMIT n`
