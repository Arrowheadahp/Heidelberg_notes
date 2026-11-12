To get f, we want to get the Inverse of A. $$f=A^{-1}g$$Sometimes when the dimensions do not match, pseudoinverse is used. $$A^{-1}_{PI}=(A^TA)^{-1}A$$
If the number of measurements > number of unknowns, the system of equations is not solvable due to random measurements errors. So we define the best solution that minimises the L2 error like in [[Squared Error]]. $$||g-Af||_2=\sqrt{\sum(g-Af)^2}$$
Minimising this error gives the pseudoinverse formula.

Alternative is to use the L1 norm but it has no closed form solution.