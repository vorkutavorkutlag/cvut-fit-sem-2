
The empty circle denotes an attribute is nullable.
A full circle denotes the attribute is not nullable.
The `U` on the left of the attribute denotes its uniqueness across the whole database.

Customers -> (dotted line) may have many reservations.
Reservation -> (full line) must have at least one customer

A relation that is mandatory from both ends does not make sense in any database, since there is no order of adding tables.

The vertical line near the triangle in the relation means that reservation is identified by the customer that it is attached to. If there are many customers, which one identifies the relation? We should remove it.

A ternary relation is not possible directly, but we can mock it in DBS portal. Many to many relationship gives us the ability to store relationship between many customers and many reservations. We could use 2 one to many relations.
We may add another entity between these three entities and connect one to many with him.

BTW, behind the scenes, a many to many relationship works exactly like this too. It's sort of like $A \implies B \land B \implies A \equiv A \iff B$ 
You can create any $n$-ary relation with this method.

Entities do not have need to have any attributes, as long as they are identified by something. If we make a good enough argument why we need it in our particular case.

Please include at least one many to many relationship in your schema in the semestral project, decomposed or not. It will be very useful in the other parts of the work.

Must have minimum 7 entities.

We have 2 submissions.