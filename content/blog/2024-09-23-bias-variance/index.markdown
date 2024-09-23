---
title: "Bias-variance decomposition"
author: "Cecina Babich Morrow"
date: "2024-09-23"
categories: ["statistics", "R"]
tags: ["statistics", "R"]
subtitle: 'A fundamental trade-off in statistics.'
summary: 'Decomposition of expected loss.'
featured: no
output: bookdown::html_document2
image:
  placement: 1
  caption: ''
  focal_point: ''
  preview_only: false
projects: []
editor_options: 
  markdown: 
    wrap: 72
---

## Inspiration for this post

Continuing my dive into the wonderful world of regression, here's an overview of the statistical theory underpinning bias-variance decomposition, one of the fundamental trade-offs in statistics. Once again, most of the material I'm showing comes from a class I took with Dr. Song Liu.

## Bias-Variance Decomposition

We've seen how increasing the flexibility of our model can lead to over-fitting, where the model performs poorly on unseen data (see [Least squares regression: Part 2](https://babichmorrowc.github.io/blog/2024-07-26-regularized_leastsquares/)). As we tried out in that post, cross-validation is a commonly used approach to determine the optimal balance between flexibility and generalizability by minimizing the average testing error resulting from training the model on different disjoint subsets of our overall dataset. In a frequentist framework, the phenomenon of overfitting as well as the strategy of cross-validation can be motivated by the concept of bias-variance decomposition.

In our training/testing framework, we have a testing error value `\(E(D_1, \textbf{w}_{LS})\)` for a model trained on `\(D_0\)`. Since we are not actually interested in the testing error for a specific testing set `\(D_1\)`, we can instead take the expectation over our entire dataset `\(D\)`:

$$
`\begin{align*}
    \mathbb{E}_D[E(D_1, \textbf{w}_{LS})] &= \mathbb{E}_D \left[ \sum_i[y_i - f(\textbf{x}_i; \textbf{w}_{LS}]^2 \right] \\
    &= \sum_i \mathbb{E}_D \left[ [y_i - f(\textbf{x}_i; \textbf{w}_{LS}]^2 | \textbf{x}_i \right]
\end{align*}`
$$

The above expression is the sum of expected loss `\(\mathbb{E}_D \left[ [y_i - f(\textbf{x}_i; \textbf{w}_{LS}]^2 | \textbf{x}_i \right]\)` over all `\(i\)` in our dataset. We make the assumption that our outcome variable is the result of some deterministic generative function plus additive noise that is independent of our input data: `\(y_i = g(\textbf{x}_i) + \epsilon_i\)`, `\(g(\textbf{x}): \mathbb{R}^d \rightarrow \mathbb{R}\)`, `\(\mathbb{E}[\epsilon_i] = 0\)`. This assumption allows us to write expected loss as the sum of three terms:

`$$\mathbb{E}_D[[y_i - f_{LS}(\textbf{x}_i)]^2|\textbf{x}_i] = \text{var}(\epsilon) + [g(\textbf{x}_i) - \mathbb{E}[f_{LS}(\textbf{x}_i)|\textbf{x}_i]]^2 + \text{var}[f_{LS}(\textbf{x}_i)|\textbf{x}_i]$$`

1. **Irreducible error** `\(\text{var}(\epsilon)\)`: the randomness of the data generation process that produces our output data
2. **Bias** `\([g(\textbf{x}_i) - \mathbb{E}[f_{LS}(\textbf{x}_i)|\textbf{x}_i]]\)`: how closely our average prediction over all datasets matches the generative function
3. **Variance** `\(\text{var}[f_{LS}(\textbf{x}_i)|\textbf{x}_i]\)`: how much our prediction is affected by the randomness of the dataset chosen

### Decomposition of expected loss

For a proof, see below:

**Theorem 1 (Decomposition of expected loss):** Expected loss can be decomposed into the sum of the irreducible error, bias, and variance, i.e. `$$\mathbb{E}_D[[y_i - f_{LS}(\textbf{x}_i)]^2|\textbf{x}_i] = \text{var}(\epsilon) + [g(\textbf{x}_i) - \mathbb{E}[f_{LS}(\textbf{x}_i)|\textbf{x}_i]]^2 + \text{var}[f_{LS}(\textbf{x}_i)|\textbf{x}_i]$$`

**Proof:** By expanding the square on the left-hand side, we get:

$$
`\begin{align*}
    \mathbb{E}_D\left[[y_i - f_{LS}(\textbf{x}_i)]^2|\textbf{x}_i\right] &= \mathbb{E}_D\left[y_i^2 - 2y_if_{LS}(\textbf{x}_i) + [f_{LS}(\textbf{x}_i)]^2|\textbf{x}_i\right] \\
    &= \mathbb{E}_D\left[y_i^2|\textbf{x}_i\right] - 2\mathbb{E}_D\left[y_if_{LS}(\textbf{x}_i)|\textbf{x}_i\right] + \mathbb{E}_D\left[[f_{LS}(\textbf{x}_i)]^2|\textbf{x}_i\right]
\end{align*}`
$$

We take the first two terms on the right-hand side separately, starting with `\(\mathbb{E}_D[y_i^2|\textbf{x}_i]\)`. We apply our data-generating assumption that `\(y_i = g(\textbf{x}_i) + \epsilon_i\)`, where `\(g(\textbf{x})\)` is a deterministic function, `\(\epsilon_i\)` is independent of `\(\textbf{x}_i\)` for all `\(i\)`, and `\(\mathbb{E}[\epsilon_i] = 0\)`. Then

$$
`\begin{align*}
    \mathbb{E}_D[y_i^2|\textbf{x}_i] &= \mathbb{E}_D\left[[g(\textbf{x}_i) + \epsilon]^2|\textbf{x}_i\right] \\
    &= [g(\textbf{x}_i]^2 + 2 g(\textbf{x}_i) \mathbb{E}(\epsilon) + \mathbb{E}(\epsilon^2)
\end{align*}`
$$

Since `\(\mathbb{E}[\epsilon_i] = 0\)`, we know that `\(\text{var}(\epsilon) = \mathbb{E}(\epsilon^2) + [\mathbb{E}(\epsilon)]^2 = \mathbb{E}(\epsilon^2)\)`. So we have `\(\mathbb{E}_D[y_i^2|\textbf{x}_i] = [g(\textbf{x}_i)]^2 + \text{var}(\epsilon)\)`.

Now consider `\(\mathbb{E}_D\left[y_if_{LS}(\textbf{x}_i)|\textbf{x}_i\right]\)`:

$$
`\begin{align*}
    \mathbb{E}_D\left[y_if_{LS}(\textbf{x}_i)|\textbf{x}_i\right] &= \mathbb{E}_D\left[[g(\textbf{x}_i) + \epsilon]f_{LS}(\textbf{x}_i)| \textbf{x}_i\right] \\
    &= g(\textbf{x}_i) \mathbb{E}_D[f_{LS}(\textbf{x}_i) | \textbf{x}_i] + \mathbb{E}_D[\epsilon]\mathbb{E}_D[f_{LS}(\textbf{x}_i)|\textbf{x}_i] \\
    &= g(\textbf{x}_i) \mathbb{E}_D[f_{LS}(\textbf{x}_i) | \textbf{x}_i]
\end{align*}`
$$

Substituting back in, we get:

$$
`\begin{align*}
    \mathbb{E}_D\left[[y_i - f_{LS}(\textbf{x}_i)]^2|\textbf{x}_i\right] &= [g(\textbf{x}_i)]^2 + \text{var}(\epsilon) - 2 g(\textbf{x}_i) \mathbb{E}_D[f_{LS}(\textbf{x}_i) | \textbf{x}_i] + \mathbb{E}_D\left[[f_{LS}(\textbf{x}_i)]^2|\textbf{x}_i\right] \\
    &= \text{var}(\epsilon) + [g(\textbf{x}_i)]^2 - 2 g(\textbf{x}_i) \mathbb{E}_D[f_{LS}(\textbf{x}_i) | \textbf{x}_i] + \left[\mathbb{E}_D[f_{LS}(\textbf{x}_i)|\textbf{x}_i]\right]^2 \\
    &- \left[\mathbb{E}_D[f_{LS}(\textbf{x}_i)|\textbf{x}_i]\right]^2 + \mathbb{E}_D\left[[f_{LS}(\textbf{x}_i)]^2 | \textbf{x}_i\right] \\
    &= \text{var}(\epsilon) + [g(\textbf{x}_i) - \mathbb{E}[f_{LS}(\textbf{x}_i)|\textbf{x}_i]]^2 + \text{var}[f_{LS}(\textbf{x}_i)|\textbf{x}_i]
\end{align*}`
$$

### So what?

Since irreducible error is out of our control, the two things we can play with in order to minimize expected loss are bias and variance. Bias and variance are both affected by the degree `\(b\)` of our feature transform. For more complex prediction functions with higher degree `\(b\)`, bias decreases but variance increases as the function becomes more sensitive to noise. Similarly, lower values of our regularization parameter `\(\lambda\)` yield more complex functions with lower bias and higher variance. Thus this decomposition provides a mathematical framework with which to understand the phenomenon of overfitting.

## Measuring performance

We want to be able to quantify how well our prediction function `\(f_{LS}\)` performs. Averaging the expected loss over all input `\(\textbf{x}_i\)` in our training set yields in-sample error: `\(\frac{1}{n}\sum_{i = 1}^n \mathbb{E}[(y_i - f_{LS}(\textbf{x}_i))^2|\textbf{x}_i]\)`. In real-world settings, we cannot compute in-sample error since the generative function `\(g(\textbf{x})\)` is unknown, as is the distribution of the additive error `\(\epsilon\)`. As an alternative, we use out-sample error, the expectation over the entire distribution of `\(x\)`: `\(\mathbb{E}_\textbf{x} \mathbb{E}[(y - f_{LS}(\textbf{x}))^2 | \textbf{x}] = \mathbb{E}_{D_0} \mathbb{E}_{p(y,\textbf{x})}[(y - f_{LS}(\textbf{x}))^2]\)`. We can approximate out-sample error using `\(\frac{1}{K}\sum_{k = 1...K} \frac{1}{n'} \sum_{(y,x)\in D_1^{(k)}} (y - f_{LS}^{(k)} (\textbf{x}))^2\)`, where `\(f_{LS}^{(k)}\)` is the prediction function trained on the `\(k\)`-th training set `\(D_0^{(k)}\)`. This expression is the same as the cross-validation error when `\(D_1^{(k)}\)` is the `\(k\)`-th disjoint subset of the dataset and `\(D_0^{(k)}\)` is the remainder of the dataset. Therefore cross-validation is a suitable way to measure the performance of our prediction function by approximating the out-sample error.

### Covariate shift in cross-validation

In cross-validation, we assume that our training data `\(D_0\)` and our test data `\(D_1\)` come from the same distribution. In the real-world, however, we often encounter situations where we would like to use a model trained on some training data to extrapolate to new data outside of the training region. The term covariate shift refers to such situations where the training and testing data have different probability distributions, but the conditional distributions of the output variable given input variables are the same. Sugiyama et al. (2007) propose a variation on cross-validation called importance weighted cross-validation (IWCV) that allows for model selection even under covariate shift.

For training samples `\(\{ (x_i, y_i) \}_{i = 1}^n\)`, a test sample `\((t, u)\)`, a loss function `\(l(x,y,\hat{y})\)` giving the discrepancy between the estimate `\(\hat{y}\)` and the true value `\(y\)` at the input value `\(x\)`, and a prediction function `\(\hat{f}(x; \hat{\theta}) = \hat{y}\)`, we can express the generalization error as `\(R^{(n)} := \mathbb{E}_{\{ (x_i, y_i) \}_{i = 1}^n, t, u} [l(t, u, \hat{f}(t; \hat{\theta}))]\)`. Typically, we would estimate `\(\theta\)` using empirical risk minimization (ERM) such that `$$\hat{\theta}_{ERM} := \text{argmin}_\theta [\frac{1}{n}\sum_{i = 1}^n l(x_i, y_i, \hat{f}(x_i; \theta))]$$` However under covariate shift when the distribution of `\(x\)` is not the same in our testing data as in our training data, ERM is no longer consistent, i.e. no longer converges in probability to the optimal parameter for our model. Sugiyama et al. (2007) propose a new method called importance weighted ERM (IWERM) that does converge: `$$\hat{\theta}_{IWERM} := \text{argmin}_\theta [\frac{1}{n}\sum_{i = 1}^n \frac{p_{test}(x_i)}{p_{train}(x_i)} l(x_i, y_i, \hat{f}(x_i; \theta))]$$` Note that the ratio of test and training densities at the training points `\(\frac{p_{test}(x_i)}{p_{train}(x_i)}\)` is referred to as importance. Since this estimate is not always efficient or stable, the authors note that it is possible to weaken the weight of the importance term by raising it to the power of a parameter `\(\lambda\)` or to add a regularization parameter `\(\gamma\)` to the empirical risk. These two options, known as adaptive IWERM and regularized IWERM, respectively, allow us to trade off between the consistency of the parameter estimate and its stability.

Those methods necessitate the tuning of `\(\lambda\)` or `\(\gamma\)` in model selection. Because of the covariate shift, however, we cannot carry out cross-validation as usual. The authors introduce the process of IWCV to address this issue, where the risk of k-fold IWCV is given as `$$\hat{R}^{(n)}_{kIWCV} := \frac{1}{k} \sum_{j = 1}^k \frac{1}{|D_j|} \sum_{(x,y)\in D_j} \frac{p_{test}(x_i)}{p_{train}(x_i)} l(x,y,\hat{f}_{D_j}(x))$$` where the `\(D_j\)` are the disjoint subsets of our training data. They find that leave-one-out IWCV provides an almost unbiased estimate of risk under covariate shift for any loss function, model, or method of parameter learning (including non-parametric methods). To carry out IWERM in practice, we need some way to estimate the importance if we do not know the test and training input density functions. The authors do this by using the empirical estimates of the densities from the training and testing data and find good performance, albeit with slightly larger error.

## References

M. Sugiyama, M. Krauledat, and K-R Müller. "Covariate Shift Adaptation by Importance Weighted
Cross Validation", Journal of Machine Learning Research, 2007.

