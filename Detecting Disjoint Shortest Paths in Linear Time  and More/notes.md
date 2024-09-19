# Detecting Disjoint Shortest Paths in Linear Time and More
[LIPIcs.ICALP.2024.9.pdf (dagstuhl.de)](https://drops.dagstuhl.de/storage/00lipics/lipics-vol297-icalp2024/LIPIcs.ICALP.2024.9/LIPIcs.ICALP.2024.9.pdf)

## $k$-Disjoint Paths ($k$-DP) problem
- We are given a graph $G$ with $n$ vertices and $m$ edges
- $k$ specified source nodes $s_1,\dots,s_k$ and target nodes $t_1,\dots,t_k$
- We are tasked with determining if $G$ contains $(s_i,t_i)$-paths which are internally vertex-disjoint

|| Directed Graphs | DAGs | Undirected Graphs |
|-|-|-|-|
| 2-DP | NP-hard | $O(m + n)$ | $\tilde O(m + n)$ |
| k-DP || $O(mn^{k-1})$ | $m^{1+o(1)}$ |


## $k$-Disjoint Shortest Paths (k-DSP) problem
- The same input as $k$-DP
- We are tasked with determining if $G$ contains $(s_i,t_i)$-**shortest** paths which are internally vertex-disjoint

|| Directed Graphs | DAGs | Undirected Graphs |
|-|-|-|-|
| 2-DSP | P | $O(m + n)$ | $O(m + n)$ |
| k-DSP | ? | $O(mn^{k-1})$ | $n^{O(k\cdot k!)}$ |


### Directed graphs
- In directed graphs, $2$-DSP can be solved in polynomial time, but no polynomial-time algorithm (or NP-hardness proof) is known for $k$-DSP for any constant $k\ge 3$.

### Undirected graphs
- For any constant $k$, $k$-DSP can be solved in polynomial time
- The current best algorithms for $k$-DSP in undirected graphs run in $n^{O(k\cdot k!)}$ time, so in general this polynomial runtime is quite large for $k\ge 3$.
- The main result of this paper is an optimal algorithm for $2$-DSP in weighted undirected graphs

## Open Problems
- Deterministic linear time algorithm
- Better lower bound or upper bound