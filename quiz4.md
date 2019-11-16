## CSC 501: Algorithms and Data Models

1. Draw a graph with a degree distribution of: <5, 3, 2, 2, 2, 2, 0>.
![graph](https://github.com/SiRumCz/CSC_501_Quizzes/blob/master/img/quiz4_q1.png)<br>

2. You are given the following relation:
Subject | Predicate | Object
:--- | :--- | :---
Xi Jinping | PresidentOf | China
Xi Mingze | isDaughterTo | Xi Jinping
Xi Jinping | isFatherTo | Xi Mingze
Xi Mingze | BornIn | Fujian
Fujian | CityIn | China
Xi Jinping | LeaderOf | Communist Party of China (CPC)
Communist Party of China (CPC) | PoliticalPartyOf | China
Xi Mingze | StudiedAt | Zhejiang University
Xi Mingze | StudiedAt | Harvard University
Zhejiang University | LocatedIn | Hangzhou
Harvard University | LocatedIn | Boston
Boston | CityIn | United States of America (USA)
Hangzhou | CityIn | China
(a) Represent the relation as a (knowledge) graph
![graph](https://github.com/SiRumCz/CSC_501_Quizzes/blob/master/img/quiz4_q2a.png)<br>
b) Show the paths matched by the following conjunctive pattern matching query:
```
x `CityIn' y ∧ w `LocatedIn' x ∧ `Mingze' v w
```
![graph](https://github.com/SiRumCz/CSC_501_Quizzes/blob/master/img/quiz4_q2b.png)<br>

You are given the following road network:
![graph](https://github.com/SiRumCz/CSC_501_Quizzes/blob/master/img/quiz4_q3.png)<br>
(a) Show this graph as an adjacency matrix, an adjacency list, and an edge list

--- Adjacency Matrix
        
||Alberni|Parksville|Skiing|Sooke|Tofino|Ucluelet|Victoria|
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
|**Alberni**|0|50|110||125|100||
|**Parksville**|50|0|100|240|||150|
|**Skiing**|110|100|0|||||
|**Sooke**||240||0|||40|
|**Tofino**|125||||0|40||
|**Ucluelet**|100||||40|0||
|**Victoria**||150||40|||0|

--- Adjacency List

**Alberni** : (Parksville, 50), (Skiing, 110), (Tofino, 125), (Ucluelet, 100)<br>
**Parksville** : (Alberni, 50), (Skiing, 100), (Sooke, 240), (Victoria, 150)<br>
**Skiing** : (Alberni, 110), (Parksville, 100)<br>
**Sooke** : (Parksville, 240), (Victoria, 40)<br>
**Tofino** : (Alberni, 125), (Ucluelet, 40)<br>
**Ucluelet** : (Alberni, 100), (Tofino, 40)<br>
**Victoria** : (Parksville150), (Sooke, 40)<br>

--- Edge List

Alberni Parksville  50<br>
Alberni Skiing 110<br>
Alberni Tofino 125<br>
Alberni Ucluelet 100<br>
Parksville Skiing 100<br>
Parksville Sooke 240<br>
Parksville Victoria 150<br>
Sooke Victoria 40<br>
Tofino Ucluelet 40<br>

(b) Calculate the global clustering coefficient (CC) of the graph

triangles: (uc, to, al), (al, sk, pa), (pa, so, vi)

triads: (to, al, sk), (uc, al, pa), (sk, pa, vi), (pa, al, so), (to, al, pa), (uc, al, sk), (sk, pa, so), (al, pa, vi)

cc = 3(3)/(3(3)+8) = 9/17

(c) Calculate the average path length (APL) of the graph. Show your work.

```
                Alberni         Parksville      Sooke   Skiing          Tofino          Ucluelet      Victoria  
Alberni         0               50              240     110             125             100             200
Parksville      50              0               190     100             175             150             150
Sooke           240             190             0       290             365             340             40
Skiing          110             100             290     0               235             210             250
Tofino          125             175             365     235             0               40              325
```

(d) Assume that all edge lengths have unit cost (i.e., cost = 1 or unweighted). Now
recalculate the average path length (APL). Show your work.

(e) How many edges are traversed by Dijkstra’s algorithm to find the shortest path
from Sooke to the ski resort at Mt Washington?
