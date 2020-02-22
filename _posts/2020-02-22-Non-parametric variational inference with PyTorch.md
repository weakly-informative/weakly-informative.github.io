## Non-parametric VI in the era of automatic differentiation

In 2012, restrictive distributional assumptions were still a downside of Variational Inference (VI). These restrictions engulfed both variational distributions and model families in which inference was possible. In this adverse scenario, Gershman et. Al. proposed Non-parametric VI (NPVI), an approach for flexible inference on non-conjugate models using mixtures of diagonal Gaussians with identical component weights as variational distributions and using a block optimization scheme to make inference possible.

Some eight years latter, automatic differentiation toolboxes (PyTorch and Tensorflow) are everywhere. 
With these tools, we could do the same with much more ease simply using the reparameterization trick and a few samples from the variational distribution.  

I've prepared a small excerpt  showing what this could look like, with an application on hierarchical logistic regression (model below).

$$ y_n | x_n \sim \text{Bernoulli}(\sigma( w \cdot x_n ))  \forall n \in \{1, \ldots, N\} $$

$$ w_d  \sim \mathcal{N}(0, \alpha_d)   \forall d \in \{1, \ldots, D\} $$

$$\alpha_d \sim \text{Gamma}(1, 0.01)   \forall d \in \{1, \ldots, D\} $$

Check out the [github repo](https://github.com/weakly-informative/NPVI) .
