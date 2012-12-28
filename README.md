Date: 12/28/2012.   Author: Anthonylife

Note: I implement the supervised topic model by modifing the GibbsLDA++ code written
by Xuan-Hieu Phan in 2007.


General idea:
    While the original paper of <Supervised Topic Model> adopted variational bayesian
to get the optimal parameters (alpha and beta) by maximizing the lower log-likelihood
bound, in this program, I use another strategy, which is very similar with Gibbs
Sampling EM algorithm. More detailedly, I calculate the posterior distribution in
E-step using Gibbs Sampling while in M-step, I utilize MLE to inference.


Gibbs Sampling implementation trick:
    1.It is better to use burning sampling strategy to get more samples to retain
the stability of the posterior distribution. While the one time samples presents
randomness which will make the final prediction sometimes bad and other times
good.
    2.When using more samples, the linear regression weights converge better.
