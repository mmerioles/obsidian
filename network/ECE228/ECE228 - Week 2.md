Overfitting - high variance, low bias
Underfitting - high bias, low variance

**Linear Regression**

$f(x) = w_0 + w_1x_1 + w_2x_2$

where $x_1$ and $x_2$ are features (age, education level, etc)
$w_0, w_1, w_2$ are parameters (weights)

Loss function defined as least squares cost function
$L(w) = \frac{1}{2} \sum_{i=1}^n (w^T x^{(i)}-y^{(i)})^2$

How to pick $w$ to minimize $L(w)$

Start with initial w and repeatedly perform
$w \leftarrow w-\alpha \nabla_w L(w)$

Batch gradient descent - scan through entire training set before taking a single step
Stochastic gradient descent - 1 sample for the update

$l(w) = logL(w)$
$\rightarrow$ $nlog \frac{1}{\sqrt{2\pi\sigma}} - \frac{1}{2\sigma^2}\sum_{i=1}^n(w^Tx^{(i)}-y^{(i)})^2$

Minimize the second term, leading to least squares for maximum likelihood estimator of w

**Logistic Regression**

Linear regression assumes $y$ is quantitative, but many cases $y$ is categorical or qualitative

Binary classification
$f(x) = \sigma (w^T x )= \frac{1}{1+e^{-w^Tx}}$

Where $\sigma(z) = \frac{1}{1+e^{-z}}$  is often called logistic or sigmoid function
- Converting prediction to a probability

Like earlier, it is easier to maximize the log-likelihood

$-l(w)$ is also known as the cross-entropy loss function

Use gradient ascent to maximize $l(w)$

$\rightarrow (y^{(i)}-f(x^{(i)}))$ same as linear regression case

$l(w)$ is concave function, guarantees convergence to global optimum

---
**Multi-class classification**

Prediction given by a *softmax* function
$$f_w(x) = softmax(Wx)$$
Where each estimated class probability is 
$$\hat y_k ^{(i)}=\frac{exp(w_k x^{(i)})}{\sum_{j=i}^Kexp(w_jx^{(i)})}$$
normalized for all the labels

$\rightarrow$ use gradient descent to minimize the cross-entropy loss function

**Linear Model Regularization Techniques**

Ridge Regression (L2 norm) - robust to small errors, sensitive to outliers

$$L_R(w)=\frac{1}{2}\sum_{i=1}^n(y^{(i)}-w_0-\sum^d_{j=1}w_jx_j^{(i)})^2+ \lambda\sum^d_{j=1}w_j^2$$
$\lambda$ is a tuning parameter

Lasso Regression (L1 norm) - handles outliers well

$$L_{\text{lasso}}(w)=\frac{1}{2}\sum_{i=1}^n(y^{(i)}-w_0-\sum^d_{j=1}w_jx_j^{(i)})^2+ \lambda\sum^d_{j=1}|w_j|$$
Only difference is the $l_2$ penalty - usually simpler to interpret (yields sparse models)

**Assessing Model Accuracy: Validation Set**
- Hold a subset of the training data to evaluate

Cross-Validation: LOOCV (Leave-one-out)
- Very expensive - need to fit $n$ times

Cross-Validation: k-fold CV
- Same idea, but use a fold k to determine the hyperparameters

Useful in classication case too by using counting mislabeled samples
