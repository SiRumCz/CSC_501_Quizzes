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

(b) Calculate the average global clustering coefficient (CC) of the graph

(c) Calculate the average path length (APL) of the graph. Show your work.

(d) Assume that all edge lengths have unit cost (i.e., cost = 1 or unweighted). Now
recalculate the average path length (APL). Show your work.

(e) How many edges are traversed by Dijkstra’s algorithm to find the shortest path
from Sooke to the ski resort at Mt Washington?
