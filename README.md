# Variational_Auto_Encoder
A Variational Autoencoder (VAE) is a type of generative model that is particularly useful for unsupervised learning tasks. It is a kind of autoencoder that learns a latent space representation of the input data and is able to generate new data samples from this latent space. The key idea behind VAEs is to combine principles from neural networks and Bayesian inference.

Key Concepts of VAEs
Autoencoder Basics:

Encoder: Maps the input data 
𝑥
x to a latent representation 
𝑧
z. In a traditional autoencoder, this mapping is deterministic.
Decoder: Maps the latent representation 
𝑧
z back to the data space to reconstruct the input 
𝑥
^
x
^
 .
The objective is to minimize the reconstruction loss between the input 
𝑥
x and the reconstructed output 
𝑥
^
x
^
 .
Variational Aspect:

Instead of mapping the input to a single point in the latent space, the VAE maps the input to a distribution over the latent space. Typically, a Gaussian distribution is used.
Encoder Output: Instead of outputting 
𝑧
z, the encoder outputs parameters of the distribution (mean 
𝜇
μ and standard deviation 
𝜎
σ).
Sampling:

To generate a sample from the latent space during training, we sample 
𝑧
z from the distribution parameterized by 
𝜇
μ and 
𝜎
σ. This sampling step introduces stochasticity.
Reparameterization Trick: To backpropagate through the stochastic sampling process, the reparameterization trick is used. This involves sampling 
𝜖
ϵ from a standard normal distribution and computing 
𝑧
z as:
𝑧
=
𝜇
+
𝜎
⋅
𝜖
z=μ+σ⋅ϵ
Loss Function:

The VAE loss function has two components:
Reconstruction Loss: Measures how well the decoder reconstructs the input from the sampled latent variable 
𝑧
z. Typically, this is the mean squared error or binary cross-entropy.
KL Divergence Loss: Measures how closely the learned latent distribution matches the prior distribution (usually a standard normal distribution). This regularizes the latent space to ensure that it follows the desired distribution.
VAE Loss
=
Reconstruction Loss
+
KL Divergence Loss
VAE Loss=Reconstruction Loss+KL Divergence Loss
Mathematical Formulation
Given an input 
𝑥
x, the encoder outputs 
𝜇
(
𝑥
)
μ(x) and 
𝜎
(
𝑥
)
σ(x). A latent variable 
𝑧
z is sampled from the distribution 
𝑁
(
𝜇
(
𝑥
)
,
𝜎
(
𝑥
)
2
)
N(μ(x),σ(x) 
2
 ). The decoder then reconstructs 
𝑥
x from 
𝑧
z.

Encoder: 
𝑞
𝜙
(
𝑧
∣
𝑥
)
q 
ϕ
​
 (z∣x) outputs 
𝜇
(
𝑥
)
μ(x) and 
𝜎
(
𝑥
)
σ(x).
Decoder: 
𝑝
𝜃
(
𝑥
∣
𝑧
)
p 
θ
​
 (x∣z) reconstructs 
𝑥
x from 
𝑧
z.
Loss Function:
𝐿
=
𝐸
𝑞
𝜙
(
𝑧
∣
𝑥
)
[
log
⁡
𝑝
𝜃
(
𝑥
∣
𝑧
)
]
−
KL
(
𝑞
𝜙
(
𝑧
∣
𝑥
)
∥
𝑝
(
𝑧
)
)
L=E 
q 
ϕ
​
 (z∣x)
​
 [logp 
θ
​
 (x∣z)]−KL(q 
ϕ
​
 (z∣x)∥p(z))


![Screenshot 2024-03-21 142353](https://github.com/UditKushwaha17/Variational_Auto_Encoder/assets/144841149/4c99a421-83cb-4326-b7a8-54f7e4398da1)
