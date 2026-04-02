Lecture 2: Foundations of Machine Learning
b

Supervised learning - build model for predicting, and supply output based on inputs
Unsupervised learning - input but no provided output (clustering)

Supervised learning example
- wage data (age, education, calendar year - to wage)
- stock market data (predict index will increase or decrease on given day)

Regression - continuous output
Classification - discrete output

Estimate $f$

Suppose we observe $Y = f(X) + \epsilon$
- $f$ is fixed but unknown function
- $e$ is a random error term

Why?
- Prediction $\hat y = \hat f (x)$ 
- Inference: relationship between response and predictor
- Maybe both - value of homes based on inputs... how much is a home with an ocean view

Predictor errors - reducible, irreducible

$E(y_0 - \hat f(x_0))^2 = (f(x_0)-\hat f(x_0))^2 + Var(\epsilon)$

How to estimate $f$
- Suppose you have n pairs of predictor-response: $\{(x,y)\}$
- Parameterize: Linear models (regression), neural networks (multi-layer perception) 

Good fitting, over-fitting, or under-fitting
- Tradeoff between flexibility and MSE

Bias-Variance Trade-Off (No free lunch)

We can expand the reducible error to the variance and bias of $\hat f(x_0)$

Variance: $E( \hat f (x_0) - E[ \hat f (x_0)] )^2$
Bias: $(E[\hat f(x_0)] - f(x_0))^2$

$\rightarrow$ We want some model with low variance and low bias


