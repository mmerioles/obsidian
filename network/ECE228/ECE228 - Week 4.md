
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

