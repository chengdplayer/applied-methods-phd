many econ papers are not estimating a causal quantity
goal of this lecture:
1. enumerate tools used to discuss causal questions
2. emphasize a multimodal approach
3. set terminology/definitions

a careful discussion of causality entails
1. a good framework to articulate assumptions
2. readers that understand the framework

Example question (medical example):
1. Notation: Neyman-Rubin causal model $Y_i(D_i)$
2. Key assumption: SUTVA, person i's outcome is only affected by their own treatment (stable unit treatment variable assignment) $$Y_i = D_iY_i(1) + (1-D_i)Y_i(0)$$
3. in potential outcome framework, missing data and causal inference are tightly linked. Any causal answer uses assumptions to infer the "missing" counterfactual
4. before diving into potential estimands, consider what the goal is 
	1. a structural parameter
	2. existence of an treatment effect
	3. a policy evaluation
5.  concepts:
	1. estimand: the quantity to be estiamted (target)
	2. estimate: the approximation of the estimand using a finite data sample
	3. estimator: the method or formula for arriving at the estimate for an estimand

Causal estimand:
1. Average treatment effect: $$\tau_\text{ATE} = E(\tau_i) = E(Y_i(1) - Y_i(0))$$
2. Average treatment effect on the treated: $$\tau_\text{ATT} = E(\tau_i|D_i=1)$$
3. Conditional average treatment effect: $$\tau_\text{CATE} = E(\tau_i|X=x_i)$$
Identification
	1. it is an invertability condition. Given data, can we always identify the value of an estimate of interest (estimand)
	2. example $E(Y_i(0)|D_i=1)$ is not identified
	3. need an assumption on the relationship between $D_i$ and $(Y_i(1),Y_i(0))$

Assumptions to identify ATE:
1. strong ignorability: $D_i$ is strongly ignorable conditional on $X_i$
	1. $(Y_i(0), Y_i(1))\perp D_i |X_i$
	2. $\exists\epsilon>0,\epsilon<Pr(D_i=1|X_i)<1-\epsilon$
	3. if D_i is randomly assigned, then this assumption is satisfied
2. when we can not estimate ATE
	1. there is unobservable variables, $(Y_i(0),Y_i(1),D_i)\not\perp|U_i$

Identification of ATE: if $D_i$ is strongly ignorable conditional on $X_i$, then
 $$E(\tau_i) = \sum_{x\in\text{supp} X_i} \left(E(Y_i|D_i=1, X_i=x)-E(Y_i|D_i=0,X_i=x)\right)Pr(X_i=x)$$
Strong ignorability provides a way to construct counterfactual from averages. 
This is all non-parametric identification. We have no model restriction on the DGP. 

Identification through DAGs

Using potential outcome, random variables' relationships are encoded functionally
In DAG, we encode the relationship between D and Y using an arrow. 
Substantially more intuitive. Equilibrium can be hard to encode.
Example: 
1. direct effect: D -> Y
2. back door path: D <- U -> Y
back door is not causal, and the effect of D on Y is not identified. 
Instead, if X is observed
1. direct effect: D -> Y
2. back door path: D <- X -> Y
Conditioning on a variable along the path blocks the path
Instead, if X is observed
1. direct effect: D -> Y
2. back door path: D -> X <- Y
backdoor collider is automatically blocked. conditioning on collider, the path is open. 
The value of DAG is laying out a model of causality, and clarifying what effects need to restricted, even in a complicated setting. 

Structural equations and causal effects (Haile 2020)




