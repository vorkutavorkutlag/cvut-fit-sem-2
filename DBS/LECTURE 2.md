
## ...Conceptual Modelling

We have probably had some experience with relations between entities. 
A pattern we use often is one to many.
If there exists the symbol of the "bird leg" on the target entity C, it means that entity D "has many C's".
Students usually have a problem with identification.
If the target entity has the identification notation (small line, scratch through the relation), it means that ... .

If both sides are dotted, it means that both entities may not be in relation with one another, meaning it is nullable. Therefore, identification with two-sided dotted line is impossible.
The identification says that the Foreign Key (the other entity) (FK) will be part of the primary key.

One of the patterns we usually use is one to many, primarily, Driver to Many Cars, where Driver begins with a dotted line, and to Cars has a hard line.
Never put identification on the dotted line, otherwise the primary key could be null.

Remember the identification relation notation by it "jumping over to the other entity" to take its foreign key, and use it as its own primary key.

You cannot use identification when it's many to many.
Usually, in many to many you should make the line dotted on both sides, as the relationship isn't that strong.
Could also use a helper entity and connect it with one to many relations on both sides to mimic many to many. As in, decompose a many to many into 2 `1:N` relations. We can also use identification dependency now, if we split it properly, and we can store some data inside of it.
Sometimes the identification dependency doesn't make sense in the **easy decomposition**, for example, in the Cinema, Program Item, Movie - example.

Incremental ID's for primary keys are usually ok, but from the theory the attribute is artificial, we adding some waste/noise into the data. For the primary key, we must be thinking if auto increment is worth it, or if we can use some other unique piece of data.

There exists a recursive relationship. For example, a zoo animal, and the "is child of" relationship. An object of some entity type can be in a relation with another object of the same entity type.

If every entity has a "child of" relation, in such a way that having a parent is obligated, you can create an artificial empty "Adam/Eve" entity. Though, making it dotted on both ends is usually more practical.

**ISA hierarchy**
Short cut of "Is a" careful, in strict ER modelling there is a requirement that exactly  one sub type instance of each super type instance exists.
Not suitable for roles (person, student, teacher, etc.), identification dependency. is better solution for this case.
Something is a type of something (but only one thing!).

The decomposition of the ISA hierarchy would be he XOR relations with some other entities. There exists an exclusive OR, saying that a movie can be either a cartoon or a documentary. It is essential that the relations are weak on one side, and hard and identified on the other.

Note that OR instead of XOR is not ISA hierarchy.

Loops means that we understand how the database is connected together. 
How can we find a loop? 
There could exist three entities, and there could be a loop of relations between them.  Also, between two entities could have loops.
If we have ISA, it also possible to make a loop, even if we don't see it (you will see it in the decomposed schema).

Are loops only problematic if we have dependent identifications? 
No, we still have problems. Identification jut means the FK starts being part of PK. The hardness of the line for example is also problematic for the existence of such schema using loops.
Loops are not impossible to get to work, though. Dotting the lines, "breaking the loop", makes the loop not dangerous, so we can make the entities without the stress of having to do circular relying.

## Relational Algebra

It is a little complicated, as we are implementing specific relational algebra in DBS portal, and the notation is not identical with some other web commands.
As in, online materials, such as ChatGPT will be using a different notation most likely.
The ideas are identical, but the "alphabet/grammar" is different.

DBS can automatically translate relational algebra query to SQL.

We have selection and projection.
For example,
Say a movie, which has a name, director, year.
How will it be physically implemented? It will be implemented as a **table**, movie, that has **columns** NAME (primary key), DIRECTOR, YEAR. These columns are domains.
Domain values are values from the same data type. From the top down, values are homogenous.
Every row is a called a **record**, it is a physical instance of the object.
It is using different domains of the same entity type, it is talking about one instance of this schema. This is the object orientated approach.

Projections is from the columns to the bottom of the entity. It is taking columns from the entity. It can be defined also, say we want to see only name and director, we can do a projection of two columns.
Selection, on the other hand, is a condition. It does not select columns without a bias like projection. It selects the rows, records, and filters them.

If we want the name of the movie that was recorded in 1985, we have to make the selection of the movies that were recorded in that year, and then make the projection for the name column.

In relational algebra, it depends on the steps which you are doing. First doing projection and then selection is dangerous, because then we lose some data. So, changing the order is dangerous. In SQL the order does not matter.

The RA is the relation schema, denoted `R(A1:D1, A2:D2, ... An:Dn)` of the name and data type pairs (string being varchar, int, etc.) It is the description of our table.

We must always be on the lookout for redundancy/duplicate attributes. 
Both for the matter of primary keys and also for the optimization of the database.

Putting data into a single line, with some separator between them, is not correct, as data must be stored atomically.

Schema key is a __minimal__ subset of attributes from $A$, which unambiguously determines each n-tuple of particular relation $R^*$.

There are also integrity constraints. For example, one movie is shown at no more than 3 cinemas. A primary and foreign key are also integrity constraints.

Queries on the schema, most important.
In relational algebra we are not manipulating the data, we are only making the queries. We have relational calculus also, and SQL.
SQL  allows insert n-tuple into relation, delete/update n-tuples in particular relation. The algorithm of manipulation operations contains check of IC.

SQL is also more vast, since it includes permissions, aggregation functions (e.g. SUM, MAX). Relational algebra is just about joining entities and operations between tables.

Funnily enough enough, in SQL, `SELECT` keyword is projection, and `WHERE` is selection.
Natural join and renaming, cartesian product, intersection, etc. will also be part of it.

The symbol for natural join is a star, and says join these two entities together via, for example, `D.DID == C.DID`
On the other hand, we could also check for other attributes. Say, taking all the drivers and cars which are currently located in the same town.
For that, we would use the cartesian product. We take every record of the driver and join it with every attribute of the car (`O(n^2)?`).
In the big set of the variants, we can say, and now, I will use condition that driver's town is equal to the car's town.

Join on is a shortcut for the cartesian product and condition.
Join might have duplicates, union does not have duplicates.
Join creates a big entity, as if gluing two tables.
Union/Intersection on the other hand, are set operations, works on identical types of entities.

