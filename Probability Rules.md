1. Conditional Probability: $$P(A|B) = \frac{P(A\cap B)}{P(B)}$$
2. A and B are Independent iff $P(A\cap B) = P(A)P(B)$
3. Multiplicative Law : $$P(A\cap B) = P(A)P(B|A)$$
4. Additive Law: $$P(A\cup B) = P(A)+P(B)-P(A\cap B)$$
5. Complement Law: $P(\bar A) = 1-P(A)$
6. Law of Total Probability: 
   If $S = B_1\cup B_2 \cup B_3 ... B_k$
   and $B_i\cap B_j=\phi,\ \forall i\ne j$
   then the collection of $B_j$ is called the partitions of S.
   If $A\subset S$ then $$A = (A\cap B_1)\cup (A\cap B_2)... (A\cap B_k)$$
   $$ P(A) = \sum_{i=1}^k P(A|B_i)P(B_i) $$