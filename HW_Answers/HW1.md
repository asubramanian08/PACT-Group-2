# <p style="text-align:center"> **PACT Homework 1** </p>
1. <br>

    1. a) Let $c_n$ be the $c$ value chooser if the $k$-supplier algorithm ran for one more iteration. That means $c_n$ would be the node farthest away from the solution set $A_s$. The cost of the solution would be that distance between $c_n$ and $A_s$.

        Let $N_c$ be $A_c \cup {c_n}$, it follows that $|N_c| = k + 1$. Lastly, let $O$ be the optimal set of suppliers and $OPT$ be the cost of $O$.

        Using PHP at least $2$ customers ($u, v$) must use the same supplier in $O$. Furthermore, the distance between $O$ and either $u$ or $v$ must be $\le OPT$. Using the triangle inequality, $dist(u, v) \le 2OPT$. Without loss of generality let $u$ be added to $N_c$ before $v$ (so $u \neq c_n$). Let $A_u$ be the list of suppliers after $u$'s closest suppler was added to $A_s$. 
        Note, since $A_u$ contains the closest supplier to $u$, $dist(u, A_u) \le OPT$. Using triangle inequality $dist(v, A_u) \le 3OPT$. Note $v = c_n$ or $c_n$ added after $v$, so $dist(c_n, A_s) \le dist(v, A_u) \le 3OPT$.

    2. b) Note sure how to prove that the approximation bound on k-supplier is 3OPT.
2. This solution for vertex cover doesn't work. Given a graph with just $2$ nodes and $1$ edge between them, both nodes are leaves. The algorithm won't pick either to be in the vertex cover, so it will be an invalid cover.
3. See the below algorithm:

    $$
    R \leftarrow V \newline
    S \leftarrow \emptyset \newline
    \text{while} \space R \neq \emptyset \space \{ \newline
    v \leftarrow \arg \max_{v \in U}{w(v)} \newline
    S = S \cup v \newline
    R = R \setminus \{u | u \in R \land w(u)dist(u,v) \le 2OPT \} \newline
    \}
    $$

    It's self explanatory why this algorithm creates a 2-approximation. It is not clear though, that $|S| \le k$.

    If $|S| > k$, then by PHP that must be at least 2 nodes ($u, v$) who share the same nearest center in the optimal solution. Let $x$ be that shared center. We know $w(u)dist(u,x) \le OPT$ and $w(v)dist(v,x) \le OPT$. Without loss of generality let $v$ be added to $S$ after $u$, so $w(u) \ge w(v)$. Rearranging and using triangle inequality, $dist(u,v) \le \frac{OPT}{w(u)} + \frac{OPT}{w(v)} \le \frac{2OPT}{w(v)} \le 2OPT$. This can't be the case because $v$ would have been removed from $R$ when $u$ was added to $S$. By looking though all values of OPT (finite for any given graph), the 2-approximate solution can be found
4. See the algorithm below (Hochbaum-Shmoys method)

    $$
    R \leftarrow V \setminus F \newline
    S \leftarrow \emptyset \newline
    \text{while} \space R \neq \emptyset \space \{ \newline
    v \leftarrow v \in R \newline
    S = S \cup v \newline
    R = R \setminus \{u | u \in R \land dist(u,v) \le 2OPT \} \newline
    \}
    $$

    For any vertex that is not $\in F$, the distance is still $\le 2OPT$. $\forall f \in F$, the distance in the optimal solution is OPT. Since every vertex in the optimal solution $\not \in F$, its distance in my solution is still $\le 2OPT$. Using triangle inequality the distance between any $f$ and my solution is $\le 3 OPT$.
5. Not sure what the approximation ratio for the greedy vertex cover is.
6. 
    1. a) For the sake of contradiction let $\deg(v) < d^*$. Let $T = T^* \setminus v$. We know that since $S^*$ is the most congested graph, $d(T) \le d(S^*)$. Doing algebra:
    $$\frac{E(T)}{|T|} \le d^*  \rightarrow \frac{E(S^*) - \deg(v)}{|S^*| - 1} \le d^* \newline E(S^*) - \deg(v) \le |S^*| \times d^* - d^* \newline E(S^*) - \deg(v) \le E(S^*) - d^* \newline \deg(v) \ge d^*$$

    This is a contradiction, therefore $\forall v \in S^*, \deg(v) \ge d^*$.

    2. b) Unless the algorithm comes up with the optimal solution $S^*$, there will be a point when it pick some $v \in S^*$ to remove from $S_n$. At that time $\forall u \in S_n, \deg(u) \ge \deg(v)$. $\sum_{u \in S_n} \deg(u) \ge |S_n| \times \deg(v)$. Using this: $d(S_n) = \frac{E(S_n)}{|S_n|} \ge \frac{|S_n| \times \deg(v) \div 2}{|S_n|} \ge \frac{\deg(v)}2$ Using the proof in part a that $\deg(v) \ge d^*$, before $v$ is removed $d(S_n) \ge \frac{d^*}2$. Since $S_\text{max} \ge S_n$ after any given iteration, $S_\text{max}$ will always be $\ge \frac{d^*}2$.