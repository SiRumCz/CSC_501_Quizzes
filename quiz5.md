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

(the, can)  
(can, can) 
(can, rust)
(can, becomes)
(rust, once)
(once, the)
(becomes, light)
(becomes, the) 
(light, rust)
(light, becomes)

total: 11

(b) How many 1-skip-grams are in the haiku?

(the, can, can)
(can, can, rust)
(can, rust, once)
(once, the, can)
(the, can, becomes)
(can, becomes, light)
(becomes, light, rust)
(light, becomes, the)
(becomes, the, can)

total: 9

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