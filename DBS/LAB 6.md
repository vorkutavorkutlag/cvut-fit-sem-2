We have a database schema. No we want to transform it into an actual database. What do we do?
If we click on the transformation button at the conceptual schema it will suggest us a table. We may change the attribute datatypes, respectively to the postgress database.
We have integers, decimals (not floats!), dates, etc.

After we've changed what we've wanted, we go to the Create Script section in the DBS portal, and paste the script that was made for us.

We underline the key, usually our ID, and denote all mandatory attributes with an asterisk before the name.
For example, 
PERSON(<u>PERSON_ID</u>, \*FIRST_NAME, \*LAST_NAME, GENDER, \*EMAIL)

We can name relations. i.e. has, owns, made, etc.

We can have multiple identifiers.

The N:M relationship between person and hotel will look like 
PERSON_HOTEL(<u>PERSON_ID</u>, <u>HOTEL_ID</u>)
If we have a 1:1 relationship, we don't need it, we just write, for example,
CUSTOMER(customer_card_number, <u>PERSON_ID</u>)

To denote the person ID is the same across the database, we have to denote
CUSTOMER\[PERSON_ID\] $\subseteq$ PERSON\[PERSON_ID\]
PERSON_HOTEL\[PERSON_ID\] $\subseteq$ PERSON\[PERSON_ID\]
PERSON_HOTEL\[HOTEL_ID\] $\subseteq$ HOTEL\[HOTEL_ID\]

For the many to one relationship, we do it in the same way as the 1:1.

In the test, transformation will be smaller.
In midterm we will have 3 or 4 entities and the relations between them.
