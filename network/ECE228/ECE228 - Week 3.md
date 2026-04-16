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
- sigmoid, tanh, ReLu, Leaky ReLu



