---
Title: Gaussian Copula Approach CDO Tranche Modelling
Template: LeafPage
---

#Gaussian Copula Approach CDO Tranche Modelling
How was the Gaussian Copula applied to the problem of pricing CDO tranche? The following was discussed by Li in his 2000 paper 'On Default Correlation: A Copula Function Approach'.

Let $\tau_i$ be a random variable that describes the default time of the $i^{th}$ asset in the underlying pool and $F(t_1) = Pr(\tau_1 < t_1)$ the marginal default time distribution function for $i = 1, ..., M$, where $M$ is the number of assets in the pool. 

To model the joint default times of all the assets in the underlying pool $F(t_1, ..., t_M)$ for all $(t_1, ..., t_M)$ (where $t_i$ is a positive real number), we make use of Sklar's theorem, which ensures the existence of a copula $C:[0,1]^M \rightarrow [0,1]$ such that 

	$F(t_1, ..., t_M) = C(F_1(t_1), ..., F_M(t_M)).$ ($+$)

The most common used version of Li's model is the **One-factor Gaussian Copula Model**, as it offers "high analytical tractability" (meaning it can be solved analytically in terms of a closed form expression) by assuming that the portfolio of the underlying assets is homogenous (see details of how this model was developed in the section **'Overview of what happened after Li's Paper, before the Financial Crisis'**). 

Each asset in the underlying portfolio belongs to a company $i$ with asset value $X_i$ for $i = 1, ..., M$. The one-factor framework means that the value of the company $i$ is modeled as 

	$X_i = \sqrt{\rho}Y + \sqrt{1-\rho}Z_i$ for $i = 1, ..., M$

	where $Y, Z_1, ..., Z_M$ are independent and identically distributed $N(0,1)$ random variables and $\rho \in (0,1)$. 
	Here $Y$ describes a kind of market risk common to all companies, 
	and $\{Z_i\}_{i = 1}^{M}$ present risks specific for each company $i$.

Now, $(X_1, ..., X_M)$ has a multivariate normal distribution with mean zero and a covariance matrix:

										$\begin{bmatrix}
										1 & \rho & \dots  & \rho \\
										\rho & 1 & \dots  & \rho \\
										\vdots & \vdots & \ddots & \vdots \\
										\rho & \rho & \dots  & 1
										\end{bmatrix}$

One of the core assumptions of the model is that there is a flat correlation between each pair of companies due to the homogeneity of the asset pool. This leads to one value of $\rho$ for the correlation of every pair of assets. This is a very strong assumption and may not have been appropriate in the context of pricing CDOs. For example, suppose that in the underlying pool of assets of a CDO there exist the following:

	- Two mortgages A and B from the same street in the UK
	
	- One mortgage C from a house in New York

While the default correlation between A and C, and B and C may be very similar, it will not be similar to the default correlation between A and B; intuitively we can see that if A defaults, B is much more likely to default (and vice versa), whereas this event will likely have to consequence whether or not mortgage C defaults.

We say that a company $i$ defaults if their asset value $X_i$ is below a certain threshold. So we link the single default time $\tau_i$ to the one-factor model by the relation $X_i = \Phi^{-1}(F_i(\tau_i))$.

Then, after the marginal distribution functions for the $\tau_i$ are determined, we can use ($+$) and the Gaussian copula to estimate the joint default distribution of the asset pool. We have then fully specified the one-factor Li model.

Click [here](http://cueimps.soc.srcf.net/course/course/finance/cdos/2cdogaussian/gaussianCDO/callibration) to see how the calibration of the default correlation in the copula function is done.

Click [here](http://cueimps.soc.srcf.net/course/course/finance/cdos/2cdogaussian/gaussianCDO/marginaldistributions) to find out how the marginal distributions are obtained.

To dicover what happened after Li's paper was published in 2000, click [here](http://cueimps.soc.srcf.net/course/course/finance/cdos/2cdogaussian/page4). 

##References

[1] *Gaussian Copula Model, CDOs and the Crisis*. PhD thesis, University of Oxford, June 2016. 

[2] David X. Li. On Default Correlation: A copula function approach. *Journal of Fixed Income,*: (4):43-54, April 2000.

