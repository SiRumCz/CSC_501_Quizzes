## Question 1
You are provided with the following table, without headers. Transform it into a maximally-normalised set of relational tables by identifying the functional dependencies; specify any integrity constraints.
```
Unlabeled Universal Relation
Carol	7	Admin	Y	NULL	5	6	Quadra St
Alice	2	Sales	Y	0	1	1	Blanshard St
Bob	9	Dev	N	NULL	3	8	Douglas St
Dave	7	Admin	Y	NULL	5	6	Quadra St
Earl	2	Sales	Y	0	3	2	Blanshard St
Frances	4	Training	N	NULL	5	5	Hillside Ave
Grace	1	HR	N	0	3	7	McKenzie Ave
```
(a) Show the normalised schema as an ER diagram<br>
(b) Show the actual table contents of each normalised relation<br>

## Question 2
You have the following two arrays S and T, a block size of 3, and 3 blocks of main memory (for which you have reserved the first block for input from S, the second block for input from T, and the third block as an output buffer.
```
S: [c, f, t, w, a, d, f, p]
T: [p, s, d, f, q]
```
(a) What is the result of joining S and T?<br>
(b) If using the Sort-Merge Join algorithm, what are the contents of main memory after 13 blocks of I/O (including reads and writes)?<br>
(c) Would a hash join be more efficient in this case? Why/why not?<br>

## Question 3
You are given the following (star schema) relations at a tour operator's office and query.
```
Packages
ResortID	FlightID	Price (CAD)
3	WS 321	$ 3200
3	AC 8055	$ 2900
1	AC 8055	$ 2700
1	WS 196	$ 3950
3	WS 196	$ 3400
2	AC 8767	$ 1950
2	DA 91	$ 1800
Resorts
ResortID	Name	Location	Rating
1	Beach Resort	Oahu	4.5
2	La Playa	Maui	3.5
3	Lago Grande	Oahu	4
Flights
FlightID	Origin	Destination	Duration
WS 321	Victoria	Oahu	6:30
AC 8055	Victoria	Oahu	8:10
WS 196	Victoria	Oahu	8:05
AC 8767	Victoria	Maui	5:50
DA 91	Seattle	Maui	6:45
```
*Query*: Retrieve the 3 cheapest packages to Oahu, indicating flight id, resort name, rating and duration.

(a) What are the join fields, selection predicates, and projections necessary to produce this result? (You are welcome, but not required, to express this in SQL.)<br>
(b) Construct the Universal Relation associated with this star schema<br>
(c) Illustrate the query result<br>
(d) Indicate which join algorithm you would use and why<br>