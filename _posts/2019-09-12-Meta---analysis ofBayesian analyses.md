## Wave your posteriors! 

Meta-analysis comprehends a bag of tools which is heavily employed in generalization studies -- in the social and medical sciences, for example --, where the main goal is to synthetize the result of several smiliar scientific studies conduced under different conditions.


For example, in 2009, [Hyde and Mertz](https://www.pnas.org/content/106/22/8801) used meta-analysis techniques to combine results from several studies concerning academic performance of adolescents and conclude *"that U.S. girls now perform as well as boys on standardized mathematics tests at all grade levels"*.

In the traditional meta-analysis results from studies are taken in as summary statistics computed directly from data. Curiously, while the intuitive  outcome of a (Bayesian) study/analysis is a posterior distribution, the analogous task of **combining posterior distributuions** has not been studied so far.

A couple of months ago, [Blomstedt et Al. (myself included) arXiv'd a novel approach](https://arxiv.org/abs/1904.04484) to this problem in which the results for each of the local studies are taken to be a pre-computed Bayesian posterior on their respective study-specific effects. We assume the local effects are exchangeable given the overall effect. Furthermore, as in common Bayesian meta-analysis, we assume the analyst places a prior over the overall efect and defines the conditional for the local effects given the overall effect. Putting these elements together, we are left with a tree-structured undirected graphical model. Then, the problem of problem of updating our belief about an effect of interest translates to marginalizing the graphical model with respect to all variables but that effect.

Our approach can be **specially useful** when the relationship between the relationship between study-specific data and the local effects is difficult to specify as a likelihood function, which poses  a challenge to the application of traditional fixed/random effects meta-analysis. This is the case, for example, when the effects of interest are **parameters of a simulator-based model** (disease outbreak dynamics, thermal fluid-flow models, etc.)

Additionally, this rather simple approach to meta-analysis still retains some of the **core properties** of classical Bayesian inference:

* **Posterior concentration.** As the number of local studies (and therefore study-specific beliefs) goes to infinity, the updated belief on the overall effect concentrates on the true value (assuming it exists).
* **Invariance under data permutation.** In our context, this means that if we perform successive updates to the global effect with beliefs for new studies, the final result does not depend on the order these results were included in the meta-analysis.


Moreover, we hope that this work serves as an incentive to scientists to share the posteriors from their studies instead of raw data, so that these can be readily used as a basis for new studies, potentialy saving considerable compute. 
