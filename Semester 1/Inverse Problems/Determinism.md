The models or inverse problems can be classified into different classes depending on the number of measurements wrt number of parameters needed to be determined.

| Determined                   | Meaning                         | Equation | Pseudoinverse    | Solution   | E(f) | Rank          |
| ---------------------------- | ------------------------------- | -------- | ---------------- | ---------- | ---- | ------------- |
| Even Determined              | Exactly enough data             | $m==n$   | $A^{-1}$         | Unique     | =0   | $r==m==n$     |
| Over Determined              | More than enough data           | $m>n$    | $(A^TA)^{-1}A^T$ | Unique     | >0   | $r==n$        |
| [[Underdetermined Problems]] | Less data than model parameters | $m<n$    | $A^T(AA^T)^{-1}$ | Non-Unique | =0   | $r==m$        |
| Mixed Determined             | Some parameters are constrained |          |                  |            |      | $r<\min(m,n)$ |

### Statistical Measures
#todo 