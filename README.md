# **Total Deep Variation for Linear Inverse Problems**

*Implementation of the paper of Erich Kobler, Alexander Effland, Karl Kunisch and Thomas Pock from Graz University*

# **Image Denoising**

The statistical interpretation of linear inverse problems allows the treatment of measurement uncertainties in the input
data $z$ and missing information in a rigorous framework. The classical estimator of $x$ given the curropted observation $z$ is given by the MAP estimator which amount to minimize the variational problem:

### $𝜀(x)$ = $𝔇(x,z) + ℛ(x)$

Here, $𝔇(x,z)$ can be identified with the minus log likelihood $-log(P(z|x)$ and the regularization term correspond to the negative log probability of the prior distribution $-log(P(x)$. Common choise is that $z$ corrupted with gaussian noise, resulting in $𝔇(x,z) = ||Ax-z||^2_2$ where $A$ can be interpreted as the downsampling matrix for super resolution tasks.
Here, for image denoising we later assume that $A = Id$, where $Id$ is the identity matrix.

For the regularizer $ℛ(x)$, Total Variation is classical and widely use. 
Total Variation (TV) is a noise removal process based on the principle that signals with excessive and possibly spurious detail have high total variation, that is, the integral of the absolute image gradient is high. According to this principle, reducing the total variation of the signal—subject to it being a close match to the original signal—removes unwanted detail whilst preserving important details such as edges.

Suppose that we are given a noisy image $z$ and wish to compute a denoised image $x$ over a 2D space. The minimization problem we are looking to solve is:

$\min_{x \in X} $ $\{{||Ax-z||^2_2}+\int_{x}||\nabla x||_1dx\}$
