This is used for [[Dimensionality Reduction]] and [[Classification]]. It aims to maximise the distance between classes while minimising the variance between each class.$$\hat k=\arg\max(\log(p(k|x)))$$$$\hat k=\arg\max(\log(p(x|k)p(k)))$$ $$p(x|k)=\prod \exp(-1/2(x-\mu)\Sigma^{-1}(x-\mu)^T) $$
The decision boundary is where the values are equal. The parameters are got by [[Maximum Likelihood]].

This is Bayes optimal when the conditions are met:
1. features of each class is optimal
2. predictors should be iid.