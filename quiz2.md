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
![quiz 2 question 1 er diagram](https://github.com/SiRumCz/CSC_501_Quizzes/blob/master/img/quiz2_q1_er.png)<br>

**Note: I need to add 1:N, N:N relations to the diagram**

table Positions has id as its primary key<br>
(b) Show the actual table contents of each normalised relation<br>
Employees

| **Name**    |
| :---------: |
| Carol       |
| Alice       |
| Bob         |
| Dave        |
| Earl        |
| Frances     |
| Grace       |

Positions

| **id**      | **title**   |
| :---------: | :---------: |
| 1           | HR          |
| 2           | Sales       |
| 4           | Training    |
| 7           | Admin       |
| 9           | Dev         |

*id is the primary key*

Offices

| **address**   |
| :-----------: |
| Quadra St     |
| Blanshard St  |
| Douglas St    |
| Hillside Ave  |
| McKenzie Ave  |

Workplaces

| **name** | **office**   |
| :------: | :----------: |
| Carol    | Quadra St    |
| Alice    | Blanshard St |
| Bob      | Douglas St   |
| Dave     | Quadra St    |
| Earl     | Blanshard St |
| Frances  | Hillside Ave |
| Grace    | McKenzie Ave |

Position_Location

| **position_id** | **location** |
| :-------------: | :----------: |
| 1               | McKenzie Ave |
| 2               | Blanshard St |
| 4               | Hillside Ave |
| 7               | Quadra St    |
| 9               | Douglas St   |

*position_id is a foreign key references Positions(id)*

Employments

| **employee_name** | **position_id** |
| :---------------: | :-------------: |
| Carol             | 7               |
| Alice             | 2               |
| Bob               | 9               |
| Dave              | 7               |
| Earl              | 2               |
| Frances           | 4               |
| Grace             | 1               |

*position_id is a foreign key references Positions(id)*

## Question 2
You have the following two arrays S and T, a block size of 3, and 3 blocks of main memory (for which you have reserved the 
first block for input from S, the second block for input from T, and the third block as an output buffer.
```
S: [c, f, t, w, a, d, f, p]
T: [p, s, d, f, q]
```
(a) What is the result of joining S and T?<br>
Ans: First output is | f | d | p | and second is | f |  |  |

(b) If using the Sort-Merge Join algorithm, what are the contents of main memory after 13 blocks of I/O (including reads and 
writes)?<br>
```
sorted S: [a, c, d, f, f, p, t, w]
sorted T: [d, f, p, q, s]
```
Ans: I assume sort of S and T took 10 blocks of I/O in total(2 reads and 2 writes for sorting S and 3 reads and 3 writes for 
sorting T). So after 13 blocks of I/O, I have:<br>
**I wrote them in wrong order, it is 2 reads and writes for sorting T, and 3 reads and writes for sorting S**

```
| S      | f | p |   |
| T      | p |   |   |
| output | d | f |   |
```

```
| S      | p |   |   |
| T      | p |   |   |
| output | d | f |   |
```

```
| S      |   |   |   |
| T      |   |   |   |
| output | d | f | p |
----- write/clear output
```

```
| S      | t | w |   |
| T      | q | s |   |
| output |   |   |   |
----- load first block of S and T
```

```
| S      | t | s |   |
| T      |   |   |   |
| output |   |   |   |
----- output is empty after two comparisons, and finished.
```

(c) Would a hash join be more efficient in this case? Why/why not?<br>
Ans: no, hash join is less efficient than sort-merge. BNL is O((8x5+3)/3) and sort-merge is O(8/3xlog(8/3)+3/3). Hash join is 
O(8/3xP+3/3) which P is 2 for array S. Since P is 2 which is larger than log(8/3)(~1.41), it is less efficient than sort 
merge algorithm.

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

(a) What are the join fields, selection predicates, and projections necessary to produce this result? (You are welcome, but 
not required, to express this in SQL.)<br>
Ans:
```
SELECT p.FlightID, r.Name, r.Rating, f.Duration
FROM Packages AS p 
LEFT JOIN Resorts AS r 
ON p.ResortID = r.ResortID
LEFT JOIN Flights AS f
ON p.FlightID = f.FlightID
WHERE r.Location = 'Oahu'
ORDER BY p.Price
LIMIT 3;
```
(b) Construct the Universal Relation associated with this star schema<br>
Ans:

ResortID|FlightID|Price|Name|Location|Rating|Origin|Destination|Duration
--- | --- | --- | --- | --- | --- | --- | --- | --- 
3|WS 321|3200|Lago Grande|Oahu|4.0|Victoria|Oahu|6:30
3|AC 8055|2900|Lago Grande|Oahu|4.0|Victoria|Oahu|8:10
1|AC 8055|2700|Beach Resort|Oahu|4.5|Victoria|Oahu|8:10
1|WS 196|3950|Beach Resort|Oahu|4.5|Victoria|Oahu|8:05
3|WS 196|3400|Lago Grande|Oahu|4.0|Victoria|Oahu|8:05
2|AC 8767|1950|La Playa|Maui|3.5|Victoria|Maui|5:50
2|DA 91|1800|La Playa|Maui|3.5|Seattle|Maui|6:45

(c) Illustrate the query result<br>
Ans:

FlightID|Name|Rating|Duration
--------|----|------|--------
AC 8055|Beach Resort|4.5|8:10
AC 8055|Lago Grande|4.0|8:10
WS 321|Lago Grande|4.0|6:30

(d) Indicate which join algorithm you would use and why<br>
I will use hash join algorithm, because the records in each table are very small and they all can fit into memory block.  
