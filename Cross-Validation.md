This is a method of getting good estimation of testing error for a hyperparameter.
### Leave one out
We leave one data point out for testing and use the rest of the data to train. We do this for each data point. Therefore we are training for n times for n data points and getting the testing error for the left out n data points. We average the n errors and get a score which is the cross-validation score.

### k-fold Cross-Validation
The idea is similar but instead of using each data point, we divide the data into k folds, train on k-1 parts and use the k-th part for testing. We then do this for each k parts. This is much less expensive since we only have to train the data for k times.

### Generalized Cross-Validation
This estimates the Leave one out Cross Validation without n separate reconstructions. The score $$V=\frac{\|(\mathbb I-A_\lambda)g\|^2_2}{trace(\mathbb I-A_\lambda)^2}$$