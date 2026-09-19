The models or inverse problems can be classified into different classes depending on the number of measurements wrt number of parameters needed to be determined.

| Determined                   | Equation | Solution   | E(f) | Meaning                             | Pseudoinverse    |
| ---------------------------- | -------- | ---------- | ---- | ----------------------------------- | ---------------- |
| Even Determined              | M=n      | Unique     | =0   | Exactly enough data                 | $A^{-1}$         |
| Over Determined              | M>n      | Unique     | >0   | More than enough data               | $(A^TA)^{-1}A^T$ |
| [[Underdetermined Problems]] | M<n      | Non-Unique | =0   | Less data than model parameters     | $A^T(AA^T)^{-1}$ |
| Mixed Determined             |          |            |      | Only some parameters are constraned |                  |

### Statistical Measures
#todo 