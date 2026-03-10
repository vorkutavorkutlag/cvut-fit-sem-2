How to output all data from a table in relational algebra/
Simply enter the name of the relation.
The order of the query result is unordered. It is a set.
It is more visible if we decide to filter only specific columns.
It can only contain a single occurrence of a relation, no duplicates.

We can make conditions in RA,
for example, with `customers(first_name="John"` $\land$ `last_name="Smith")`

In SQL we can have duplicates, but in RA, we operate in sets, so we have to make sure these sets are unique.

To list all customers who do not hold a relation, we take all the customers minus the customers that hold the relation.
For example, `customer[customer_id]` is all the customers, then `customer_reservations[customer_id]` is all the customers who made the reservation, and then we can get the difference between the two queries.
The final query then would be `customer[customer_id] \ customer_reservations[customer_id]`

In practice, we wouldn't work with only the customer ID. we can join it back with customers. Then, we can have the natural product with the customers.
`{customer[customer_id] \ customer_reservations[customer_id]} * customers`
Swapping the order of the joins creates problems. Tread carefully.

A note on the efficiency.
The server is pretty clever with algorithms. We focus on describing what we want, how the database server will achieve that is its problems. There are more detailed courses in this faculty about this. Though, essentially, we don't need to worry about optimizing our queries that much right now.
It might look inefficient but the server isn't actually processing it line by line.

The natural product looks at how columns are named, it does not look at primary key or foreign key. Joining two datasets on the same attribute makes sense.

If we want to display each customer who made a booking with the name of the hotel that the booking was in. How could we do something like that? 
We would like to join customers, customer_reservations, and reservations.

`customers * customer_reservations * reservations`
This would join all of them together into tuples. 
Now we can just join it with hotels, right? Can't! We have reservation, hotel IDs, why can't we join with hotels? They have the same IDs. But... It has a conflict in choosing which IDs to use. 
For example, we can have the contact address email of the hotel and the email of the customers, both called `email`, so the natural join will be joining in on hotel ID and email, and there are no routes that would have both of them, so we get an empty results.

Relational Algebra has an operation that can help us. We can rename the attribute as we go, with the arrow operator, `hotels[email -> hotel_email]`. This will show us the column of the hotel emails.
It changes it just for the query, it does not touch the actual database.

We can force priority with curly brackets `{}` around blocks of the query.

`customers * customer_reservations * reservations * hotel[hotel_id, name, city, street_name, country, stars, email -> hotel_email]`

If you have a database with the same column names, be careful, since the natural product looks at the names.

The database for the midterm might have this issue, so know still how to solve this.

We can also tell the system on which column we want to do the join. We can do the joins by brackets instead of an asterisk, and in the brackets we can write the specific key.
`customers * customer_reservations * reservations[reservations.hotel_id=hotels.hotel_id]hotel`

Then it will automatically rename the email columns to avoid duplicates.

What if we only wanted to show the first name, last name, and hotel name?
We can wrap it in curly brackets and project.
`{customers * customer_reservations * reservations[reservations.hotel_id=hotels.hotel_id]hotel}[first_name, last_name, name]`

Next up we will discuss C-type and D-type queries.

How do we denote that as specific query if of some category?
D1, for example, is relationship with everything.
We can denote that by clicking and pressing Add Category and selecting our categories. It is one of the categories it cannot detect for you, otherwise most of them can be detected through RA/SQL.

