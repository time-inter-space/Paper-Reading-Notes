# A Faster Algorithm for Pigeonhole Equal Sums
[LIPIcs.ICALP.2024.94.pdf (dagstuhl.de)](https://drops.dagstuhl.de/storage/00lipics/lipics-vol297-icalp2024/LIPIcs.ICALP.2024.94/LIPIcs.ICALP.2024.94.pdf)

## Pigeonhole Equal Sums
- Given $n$ positive integers $w_1, \dots, w_n$ of total sum $\sum_{i=1}^n w_i < 2^n−1$
- The task is to find two distinct subsets $A,B \subseteq [n]$ such that $\sum_{i\in A}w_i = \sum_{i\in B}w_i$

## Previous work
- A simple binary search with meet-in-middle solves Pigeonhole Equal Sums in $O^∗(2^{n/2})$ time
- Another $O^∗(2^{n/2})$ time algorithm based on dynamic programming
- [LIPIcs.ESA.2022.6.pdf (dagstuhl.de)](https://drops.dagstuhl.de/storage/00lipics/lipics-vol244-esa2022/LIPIcs.ESA.2022.6/LIPIcs.ESA.2022.6.pdf)

## This paper
- Pigeonhole Equal Sums can be solved by a randomized algorithm in $O^∗(2^{0.4n})$ time
- Pigeonhole Equal Sums can be solved by a randomized algorithm in $𝑂^∗(2^{0.75n})$ time and $poly(n)$ space

## Open Problems
- Deterministic algorithms
- A modular variant of the Pigeonhole Equal Sums problem: Given $n$ positive integers $w_1, \dots, w_𝑛$ and a modulus $m\le 2^n−1$, find two distinct subsets $A,B \subseteq [n]$ such that $\sum_{i\in A}w_i \equiv \sum_{i\in B}w_i\ (\mod m)$
