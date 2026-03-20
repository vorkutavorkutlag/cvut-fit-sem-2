Implementing C/D queries...

In a D query, everyone is applied to a relationship.
"Guests that stayed at all the rooms in the database."
When we print just the ID and whatnot that doesn't change.
"Students that are enrolled in all the courses."

A C query means the relationship already exists in a limited. 
Guests that only stayed in a hotel that is in Prague.
"Students that are enrolled in the DBS course"
"Customers that only made a reservation that have a review."


Another C type: 
Customers ONLY staying in HOTEL_ID=1

The guests never stayed in a hotel that doesn't meet the criteria we mentioned.
That is why it's C type.

Let's find customers that have reservation for hotel id = 1.
`customers*customer_reservations*reservations`
Here we see the full table with all the information.
Now, to make a selection,
`{customers*customer_reservations*reservations}(hotel_id=1)`
If we didn't do the curly brackets, we would have filtered the reservations only to the hotel ids and then join, but with the curly brackets, the order is different. In this case it results in the same thing, but still important distinction.

Now project only the customer ID.
`{customers*customer_reservations*reservations(hotel_id=1)}[customer_id]`

This is not a C type yet!
Because the customers may have stayed in other hotels too.

Customers who stayed in different hotels:
`{customers*customer_reservations*reservations(hotel_id!=1)}[customer_id]`

Customers who only stayed in hotel_id=1, we do it with set subtraction.
`{customers*customer_reservations*reservations(hotel_id=1)}[customer_id]`
`\`
`{customers*customer_reservations*reservations(hotel_id!=1)}[customer_id]`

THIS is a C-type query.
Every C-type query can be made similarly to this. The pattern.

// side-note, we can remove customers as customer_reservations already includes
// customer_id...

What if we wanted to change it to customers that only stayed in hotels that are in Prague?

`{customer_reservations*reservations*rooms*hotels(city = 'Prague')}[customer_id]`

Not a C type yet as it includes customers who stayed in other cities as well (maybe)

// we can remove rooms because of the way it is identified in the schema
// but that is too complicated for now imo...

Finally,
`{customer_reservations*reservations*rooms*hotels(city = 'Prague')}[customer_id]`
`\`
`{customer_reservations*reservations*rooms*hotels(city != 'Prague')}[customer_id]`

What if we want to project all the information on the customers?
We can join it with customers again.
```
{
{customer_reservations*reservations*rooms*hotels(city = 'Prague')}[customer_id]
\
{customer_reservations*reservations*rooms*hotels(city != 'Prague')}[customer_id]
} * customers
```

Natural join compares column names, so it looks at the customer_id column. It looks at the customers with the same name in customers, being customer_id.
When it doesn't have any matching attributes, it joins everything with everything.
It won't tell you "I can't join this", it will join on everything. It will be a little meaningless data...

When there's more than one matching column name, it will match all of them with all of them.

...

We want to display customers that have a reservation in all hotels.
That will be our D-type.

We will be using the cartesian product for this.
I will be using `x` for the symbol, but it's actually $\times$ 

It will give us all the possible combinations, and we will subtract it with something.
First we are finding customers that don't have a reservation in one hotel.
We can first get all possible combinations of customers and hotels, and then remove the other combinations.

If we wanted all possible combinations between customer_id and hotel_id.
`{customers x hotels}[customer_id, hotel_id]`
This we can do directly, since we are not joining on any particular attributes. We are just computing all possible combinations.
Which of these combinations actually happened, and subtract them.

We want to find combinations that didn't happen, so we can subtract it later on.
...
`{customers*customer_reservations*reservations}[customer_id, hotel_id]`
These are the ones that actually happened.

Then, bookings that never happened:
```
{customers x hotels}[customer_id, hotel_id]
\
{customers*customer_reservations*reservations}[customer_id, hotel_id]
```

In SQL we can implement this query in a different way that is more efficient. Later.

All the customer IDs which are here should not be in the result.
Then, all customers minus this:
```
customers[customer_id]
\
{
	{customers x hotels}[customer_id, hotel_id]
	\
	{customers*customer_reservations*reservations}[customer_id, hotel_id]
}
```

And then, to get all the information on these customers, we join it back with customers
```
{
customers[customer_id]
\
{
	{customers x hotels}[customer_id, hotel_id]
	\
	{customers*customer_reservations*reservations}[customer_id, hotel_id]
}
} * customers
```


In RA, we have a shortcut for this called relational division.
I will be writing `div` instead of $\div$ .

`{customer_reservations*reservations*hotels}[customer_id, hotel_id] div hotels[hotel_id]`

These two queries are entirely equivalent. Both are D-type queries and will be accepted.

There are 2 possible D-types per three-tuple of entity, relation, entity (as it can go backwards).
