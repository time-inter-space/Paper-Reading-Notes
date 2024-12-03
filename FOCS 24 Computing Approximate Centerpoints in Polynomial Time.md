# [Computing Approximate Centerpoints in Polynomial Time]([Computing Approximate Centerpoints in Polynomial Time | IEEE Conference Publication | IEEE Xplore](https://ieeexplore.ieee.org/abstract/document/10756130))

Yeshwanth Cherapanamjeri, Massachusetts Institute of Technology.



### Problem Settings

Given a set of points, a centerpoint is a point such that any hyperplane passing through it divides the point set into roughly balanced pieces.

Formally, given a point set, $X = \{x_i \in \mathbb{R}^d\}^n_{i=1}$, the centerpoint is any point $x$ which satisfies the following: 
$\forall v \in \mathbb{R}^d : \text{Depth}(X,x,v) \geq \frac{1}{d+1}$ where 
$Depth(X,x,v) := \min \{\frac{1}{n}\sum_{i=1}^n\mathbb{1}\{⟨x_i,v⟩ \leq ⟨x,v⟩\}, \frac{1}{n}\sum_{i=1}^n\mathbb{1}\{⟨x_i,v⟩ ⩾ ⟨x,v⟩\}\}$.

You can understand the conception in the one-dimensional setting easily, because the centerpoint in 1-dimension just divides all points into fifty-fifty, just the median. 

A natural question is that can we get a point with depth $1/2$ for a higher dimension? The answer is NO. Helly proves that $\frac{1}{d+1}$ is the best achievable in the worst case in 1923.



As a consequence of Helly’s theorem in convex geometry, such a point actually exists for all point sets. Then the problem is that how can we efficiently compute the centerpoints.



### History

The best algorithms for this problem only guarantee a point with depth $Ω(1/d^2)$. (Approximating center points with iterated radon points, 1993)



### Preliminaries: approximate centerpoints

Define the directional quantiles, $\forall ||v||=1:q_v:=\min\{x:\#\{i:⟨x_i,v⟩ \leq x\}\geq \Omega(\frac{n}{d+1})\}$. Then a valid point with depth $\Omega(1/d)$ can be defined by $\forall ||v||=1:⟨x,v⟩ \geq q_v$. For error parameter $\varepsilon \gt 0$, an approximate centerpoint will satisfy $\forall ||v||=1:⟨x,v⟩ \geq q_v-\varepsilon$.



### Results

There exists an algorithm computing an $\varepsilon$-approximate centerpoint in time poly($n,d,1/\varepsilon$).



### Approach

1. Compute an approximate gradient
2. Use the approximate gradient to update the estimate

#### A simple example to show how an iteration works

Suppose $0$ is a point of low depth, and let $v$ be a direction with low depth such that $\#\{i:⟨X_i,v⟩<0\}\leq\frac{n}{4d}$. We should compute an approximate gradient $\hat{g}$ such that $⟨\hat{g},v⟩\geq\gamma>0$ for $\gamma$ bounded away from $0$ for all such $v$.

The writer uses **Radial Isotropic Transformation** to compute $\hat{g}$.

We say that a linear transformation $R : \mathbb{R}^d \rightarrow \mathbb{R}^d$ places a set of points $u_1,\dots,u_n \in \mathbb{R}^d$ in Radial Isotropic Position if $\frac{1}{n}\sum^n_{i=1}\frac{Ru_i}{||Ru_i||}⊗ \frac{Ru_i}{||Ru_i||} = \frac{I}{d}$.

They prove that the Radial Isotropic Transformation exists almost everywhere and can be (approximately) computable in polynomial time.

Then $\hat{g}=\frac{1}{n}\sum_{i=1}^n\frac{x_i}{||Rx_i||}$ is the required approximate gradient.

The process is like gradient descent.



### Open questions

1. Can the poly($1/\varepsilon$) be improved to logarithmic dependency?
2. Beyond the worst-case analysis, can we get better depth guarantees for non-worst case point sets?