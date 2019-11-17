## CSC 501: Algorithms and Data Models

1. You are given the following unordered sets, corresponding to tech-heavy stock portfolios:
```
{{MSI,FB,GOOGL,TSLA},
{GOOGL,IBM,MSI},
{FB,UBER,TSLA},
{AAPL,NVDA,IBM,MSI},
{INTC,AMZN,AAPL,GOOGL},
{INTC,IBM,NVDA},
{AAPL,AMZN,NVDA,INTC}}
```
(a) Draw a trie that stores individual stocks as nodes and full portfolios as paths from the root to a unique leaf (Hint: You will probably not want to use the given orders.)

(b) Illustrate how you would use the trie that you have drawn to retrieve all mutual funds containing both AMZN and AAPL (Note: If you want to support arbitrary queries, you will need an auxiliary data structure, but this specific query conveniently doesn’t require that.)

2. You are given the following haiku:
```
the can can rust once
once the can becomes light rust
light becomes the can
```
(a) How many bigrams are in the haiku?
```
includes newlines:

(the, can)
(the, can)
(the, can)
(can, can)
(can, rust)
(rust, once)
(once, the)
(can, becomes)
(becomes, light)
(light, rust)
(light, becomes)
(becomes, the)

total: 12
```
with newlines: SUM(i)(li-1) = 4+5+3 = 12<br>
without: li-1 = 15-1 = 14

(b) How many 1-skip-grams are in the haiku?
```
12 0-skip-grams (0-skip-grams is a subset of 1-skip-grams)
(the, can, can)
(can, can, rust)
(can, rust, once)
(once, the, can)
(the, can, becomes)
(can, becomes, light)
(becomes, light, rust)
(light, becomes, the)
(becomes, the, can)

total: 12+9 = 21
```
with newlines: SUM(i)(li-1+li-2) = SUM(i)(2li-3) = 7+9+5 = 21<br>
without: 2li-3 = 2(15)-3 = 27

(c) Draw a |V| × |V| transition matrix and a graph to illustrate the transition probabilities for each bigram in the corpus

(d) Draw a second |V| × |V| matrix where a cell (i, j) is coloured:
```
white if pr(i,j) = 0
blue if pr(i,j) < pr(i) · pr(j)
green if pr(i,j) = pr(i) · pr(j)
red if pr(i,j) > pr(i) · pr(j)
```

(e) What is the average mutual information (AMI) of this corpus?

(f) What is a homonym?

(g) Calculate TF-IDF vectors for each of the three lines of the haiku and report which
two lines are most similar
```
TF vectors
the can rust  once  becomes light
1   2   1     1     0       0
1   1   1     1     1       1
1   1   0     0     1       1

IDF vector:
the     can     rust    once    becomes light
lg(3/3) lg(3/3) lg(3/2) lg(3/2) lg(3/2) lg(3/2)

TF-IDF TF*IDF:
the can rust      once      becomes   light
0   0   1*lg(3/2) 1*lg(3/2) 0         0
0   0   1*lg(3/2) 1*lg(3/2) 1*lg(3/2) 1*lg(3/2)
0   0   0         0         1*lg(3/2) 1*lg(3/2)

v0 dot v2 = 0
v0 dot v1 = 2lg(3/2)
v1 dot v2 = 2lg(3/2)

line 1 and 2 are most similar
```
