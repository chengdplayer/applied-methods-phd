main points:
1. propensity score
	1. A framework for discussing subpopulation being treated
	2. a way to link to an underlying economic model
2. interference and violations of SUTVA

 Recall Horvitz-Thompson estimator

In the strong ignorability condition, X_i can be very high dimensional
Rosenbaum-Rubin shows that
$$(Y_i(1), Y_i(0)) \perp D_i | X_i \implies  (Y_i(1), Y_i(0)) \perp D_i | \pi(X_i)$$
Exact matching is impossible, this creates bias. How to pick up matched units. The imputation creates issues. 

IPW estimator/stable IPW estimator

Even if knowing the true propensity score, it is still better to use the estimated propensity score. The difference between estimation and true score is informative. 

Contrasting propensity scores with regression
Aronnow and Miller: use linear regression to impute missing value
(one way of inferring missing value)

Empirical example
The tool does not fit in all situation, needs outside knowledge for subsampling

The problem with propensity score
Unobservable creates problem, but we also need it to create variation in D
Think about Heckman 1997










