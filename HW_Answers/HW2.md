# <p style="text-align:center"> **PACT Homework 2** </p>
1. Let team $A$ be the team the wins and let team $B$ be the team that loses the World Series. The probability exactly $6$ games to be played with a particular winners in $\frac{1}{2^6}$. Additionally we know that team $A$ must win the last game, so in first $5$ games team $A$ wins $4-1=3$ times and team $B$ wins $2$ times. Using the sticks and crosses method, we know there are ${3+2\choose3} = {5\choose3}$ ways to order $A$ and $B$'s games. Finally there are $\frac{5\choose3}{2^6}$ ways for team $A$ to win in $6$ games. Since either team could win we $\times 2$. The final answer is $2\times\frac{5\choose3}{2^6} = \frac{20}{64} = \frac5{16}$.
2. Let $A$ be the event that road $a-c$ is available. Let $B$ be the event that roads $a-b$ and $b-c$ are available. We want to find $P(A \cup B)$ Using the property of Inclusion-Exclusion $P(A \cup B) = P(A) + P(B) - P(A \cap B)$. Since any road shuts with probability $p$: $P(A)=1-p$, $P(B)=(1-p)^2$, and $P(A \cup B)=(1-p)^3$. Plugging this in: $P(A \cup B)=$
    $$(1-p)+(1-p)^2-(1-p)^3$$
    $$(1-p) + (1 - 2p + p^2) - (1 - 3p + 3p^2 - p^3)$$
    $$(2 - 3p + p^2) - (1 - 3p + 3p^2 - p^3)$$
    $$1-2p^2+p^3$$
3. Let $n$ be the number of Vincent children and $g$ be the number of Vincent girls. We know the probability of seeing $2$ girls is $\frac{\binom{g}2}{\binom{n}2} = \frac12$. Simplifying and expanding: $2g(g-1)=n(n-1)$. After trying values we find $n=4$ and $g=3$, since $2 \times 3 \times (3-1) = 4 \times (4-1)$.
4. Since each teams has an equal probability of winning we can calculate our probability "after" the first game is played. Let team $A$ and $B$ be the teams the won and lost the first game respectively.

    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Case 1 - Win after $2$ more games: $\frac{\binom10}{2^2}$

    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Case 2 - Win after $3$ more games: $\frac{\binom21}{2^3}$

    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Case 3 - Win after $4$ more games: $\frac{\binom32}{2^4}$

    The answer is the sum of all these case: $\frac{\binom10}{2^2} + \frac{\binom21}{2^3} + \frac{\binom32}{2^4} = \frac14 + \frac28 + \frac3{16} = \frac{11}{16}$
5. The answer is $P(X=1 \mid X\ge1)$. The algebra follows:
    $$\frac{P(X=1 \cap X\ge1)}{P(X\ge1)}$$
    $$\frac{P(X=1)}{1-P(X=0)} = \frac{3 \times \left(\frac16 \times \left(\frac56\right)^2\right)}{1 - \left(\frac56\right)^3}$$
    $$\frac{\frac{75}{6^3}}{\frac{6^3 - 5^3}{6^3}} = \frac{75}{6^3-5^3} = \frac{75}{91}$$
6. <br>

    (a) $\Omega = $ {(Fair, T, T), (Fair, T, F), (Fair, F, T), (Fair, F, F), (Two-Heads, T, T)}

    (b) Let $H$, $T$, and $F$ be the event that Alice flips two heads, draws a two-heads dice, and draws a fair dice respectively. We want to find $P(T \mid H)$:
    $$P(T \mid H) = \frac{P(T \cap H)}{P(H)} = \frac{P(T \cap H)}{P(H \cap F) + P(H \cap T)}$$
    $$\frac{P(T) \times P(H \mid T)}{P(F) \times P(H \mid F) + P(T) \times P(H \mid T)}$$
    $$\frac{\frac12 \times 1}{(\frac12 \times \frac14) + (\frac12 \times 1)} = \frac{\frac12}{\frac18 + \frac12} = \frac4{1+4}= \frac45$$
7. Let's call the archers $A$ and $B$ where archer $A$ shoots first. Let $T$ be the event that the target is hit once. Let $H_A$ and $H_B$ be the events that archers $A$ and $B$ hit the target respectively. We want to find $P(H_B \mid T)$:
    $$\frac{P(H_B \cap T)}{P(T)} = \frac{P(H_B)\times P(\overline{H_A})}{P(H_A)P(\overline{H_B})+P(H_B)P(\overline{H_A})}$$
    $$\frac{0.6 \times (1-0.3)}{0.3(1-0.6) + 0.6(1-0.3)} = \frac{\frac6{10}\times\frac7{10}}{\frac3{10}\times\frac4{10}+\frac6{10}\times\frac7{10}}$$
    $$\frac{6\times7}{3\times4+6\times7} = \frac{42}{12 + 42} = \frac{42}{54} = \frac{7}{9}$$
8. Let $C_i$ be the event that the $i^\text{th}$ coin is picked. Let $H$ be the event that a selected coin flips heads. We want to find $P(C_5 \mid H)$:
    $$P(C_5 \mid H) = \frac{P(C_5 \cap H)}{P(H)} = \frac{P(C_5)\times P(H \mid C_5)}{\sum_{i=1}^{10} \frac1{10} \times \frac{i}{10}}$$
    $$\frac{\frac1{10} \times \frac5{10}}{\frac{\sum_{i=1}^{10} i}{100}} = \frac{1 \times 5}{\sum_{i=1}^{10} i} = \frac5{55} = \frac1{11}$$
9. <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$A$: The event an American writes the word "valor".
    <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$E$: The event an Englishman writes the word "valour".
    <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$V$: The event a vowel is randomly selected from the written word.

    We want to find $P(E \mid V)$:
    $$P(E \mid V) = \frac{P(E \cap V)}{P(V)} = \frac{P(E)\times P(V \mid E)}{P(V \cap A) + P(V \cap E)}$$
    $$\frac{P(E)\times P(V \mid E)}{\left(P(A)\times P(V \mid A)\right) + \left(P(E)\times P(V \mid E)\right)}$$
    $$\frac{40\% \times \frac36}{(60\% \times \frac25) + (40\% \times \frac36)} = \frac{\frac15}{\frac6{25} + \frac15} = \frac5{6 + 5} = \frac5{11}$$
10. Unattempted, my guess is $\frac15$.
11. Pairwise independence:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Case 1 - prove $P(E_{ij} \cap E_{kl})=P(E_{ij})\times P(E_{kl})$: $P(E_{ij} \cap E_{kl}) = \frac1{36}$ and $P(E_{ij})=P(E_{kl})=\frac16$.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Case 2 - prove $P(E_{ij} \cap E_{ki})=P(E_{ij})\times P(E_{ki})$: $P(E_{ij} \cap E_{ki}) = \frac1{36}$ and $P(E_{ij})=P(E_{ki})=\frac16$.

    Not mutually independent: $P(E_{ij})=P(E_{ik})=P(E_{jk})=\frac16$ and $P(E_{ij} \cap E_{ik} \cap E_{jk} = \frac1{36})$. Therefore, $P(E_{ij} \cap E_{ik} \cap E_{jk}) \neq P(E_{ij})\times P(E_{ik})\times P(E_{jk})$.
12. Not sure how to solve this.