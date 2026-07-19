Mixture of Experts
- Replace one large MLP with many small "expert" MLPs

Modified Attention Mechanisms
- KV Cache Problem -  need to reduce KV cache during inference
- Multi-Head Attention -> grouped query attention
- GQA: Middle ground
	- reduces KV cache by a factor of $\frac{n_h}{G}$
- Sparse Attention: using local patterns

LM Heads and Sampling

---


---
Neural ODEs
=
Recall - ODEs have 2 components
- some dynamics function
- an initial condition

--> ode solutions are unique

we want the neural ode to be solver-independent

adjoint method
- stores full trajectory
- resuse standard ODE solvers to compute gradients during backward pass

generative modeling
- continuous normalizing flows
