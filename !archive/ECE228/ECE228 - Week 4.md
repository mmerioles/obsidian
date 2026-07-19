
Convolutional Neural Networks

MLP for vision data?
- dimensions can get really big (100 x 100 x 3 = 30,000) for 100px rgb image
Motivation
- Use spatial structures in image data to reduce amount of learning/num of parameters
- Translation invariance, rotation/viewpoint invariance

Convolution formula
$$(f \ast g)(x, y)= \sum_i \sum_j f(x+i, y+j)g(i,j)$$
- $f$ is the input (image) and the function just picks a patch
- $g(i,j)$ represents each element of the filter

---

If we implement CNN, then with 100 filters of 3 x 3 x 3 size, we only need 2800 parameters

Pooling layer (Max)
- Reduce feature dimension $\rightarrow$ reduce number of learning parameters

Classic Networks

AlexNet - 1st place in 2012 ImageNet competition (17% test error) - uses ReLU, max pooling, padding, dropout regularization
VGG-16 - 1st place in 2014 ImageNet competition (7.32% test error)
ResNet - 1st place in 2015 ImageNet - (3.57%)  deep neural networks
- Idea: shortcut information forward layers to help with feedforward and backpropagation of the gradient - allows for training of very deep neural networks

Tip: use classic architectures that are pretrained on large datasets

Temporal data - (time-series, wind speed, vehicle trajectory, etc)
Sequence Data - locality, translation invariance

Recurrent Neural Network
- time series data is fed within hidden layer
- Backpropagation through time (BPTT)
- Vanishing gradient problem

Gated Recurrent Units (GRU)
- Add "trainable memory to network"
- Update gate - to manage old state
- Reset gate - to reset

Long Short-Term Memory (LSTM)
- Input gate, forget gate, output gate