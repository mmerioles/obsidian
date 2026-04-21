**Neural Network Basics**

Forward Computation of Logistic Regression
- Linear model $\rightarrow$ sigmoid function $\rightarrow$loss function
$$z=w^Tx +b \rightarrow \hat y = \sigma(z) \rightarrow L(y,\hat y)$$
One Hidden Layer Neural Network (2-layer)
- MLP 
- Forward Computation: 
	- Split each neuron into pre-activation $z^{[1]}_1$ and $a^{[1]}_1$
	- Then there is $z^{[2]}$ with $a^{[2]}$ outputting to $\hat y$
	
Backward pass -- usually auto calculated by libraries

Activation Function
- Refers to how weighted sum is transformed to (often nonlinear) output
- Without it, can only represent a linear relationship between input and output
- sigmoid, tanh, ReLU, Leaky ReLU

---
Batch vs Mini-batch Gradient Descent
- Batch - process all N samples in one step (monotonically decreasing loss fn)
- Mini-batch - split training set into mini-batches of size B (noisy loss fn)
	- In practice pick $1<B < N$ (typically $B\in \{64,128,256,512\}$)

Optimization Algorithms

Momentum
- Compute $dW, db$ on current mini-batch
- Update momentum (exponential moving average of past gradients)
	- Update: $V_t = \beta V_{t-1} + (1-\beta)g_t$
- Update parameters
- Bias Correction: $V_t = (1-\beta)\sum_{i=1}^t\beta^{t-1}g_i$
	- $V_t^{corrected}=\frac{V_t}{1-\beta^t}$

Root Mean Squared Propagation (RMSprop)
- Keep track of gradient scale, and create an adaptive learning rate
	- $W:=W-\alpha \frac{dW}{\sqrt{S_{dW}+\epsilon}}, b:=b-\alpha \frac{db}{\sqrt{S_{db}+\epsilon}}$
- Large gradients $\rightarrow$ smaller effective learning rate
- Small gradients $\rightarrow$ larger effective learning rate

Adam Optimizer (Adaptive Moment Estimation)
- Combines best properties of Momentum and RMSprop

Learning Rate Decay
- Reduce by a factor after every few epocs
- Stairwise decay and Cosine decay are most common today

Random Initialization
- Xavier (best for tanh, sigmoid)
- Kaiming (best for ReLU, LeakyReLU)

Deep Learning Regularization
- Early stopping - stop training before overfitting
- Dropout - randomly zero out neurons
- Batch Normalization - normalize hidden  layers
- Weight Decay / $L_2$ Regularization
- Data Augmentation
