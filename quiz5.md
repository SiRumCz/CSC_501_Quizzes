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