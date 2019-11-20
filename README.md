# kfoldann
Implements KFold cross-validation for Artificial Neural Networks (ANN). The implementation is essentially the [algorithm 5.1](http://www.deeplearningbook.org/contents/ml.html) pseudo-code to code translation. I inspired myself also in the functions depicted in Figure 18.8 of the AI book[2]. Note that the [algorithm 5.1](http://www.deeplearningbook.org/contents/ml.html) is more general than the algorithm depicted in Figure 18.8. While the former employs a more general loss function, the latter performs model selection based only on hypothesis size.

- One of the reasons why I implemented this protocol is as a comprehension exercise. In particular I was able to untangle following issues:

  --Given an single task scenario with continuous output, how estimate generalization error using K-fold cross-validation? I was     specially tricked by this setting: in every iteration i \in {1,2,...,K} there is a training set TS and a validation set VS; VS contains N elements, say.

    -- Should we 

      --- Possibility A: 1) first average on the current (iteration i) validation set and then 2) average over folds?

    -- or

      --- Possibility B: 1) first, for every pattern, collect statistics on all folds and then 2) average for every pattern?

    It turned out to be a reasoning mistake. After having performed all the iterations, every pattern is used ONLY ONCE for validation. Therefore, there is no possibility B. The error has to be calculated using A.


# Refences
[1] Goodfellow, I., Bengio, Y., & Courville, A. (2016). Deep learning. MIT press.

[2] Russell, S. J., & Norvig, P. (2016). Artificial intelligence: a modern approach. Malaysia; Pearson Education Limited,.
