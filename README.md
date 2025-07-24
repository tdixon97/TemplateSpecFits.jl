# TemplateSpecFits.jl

[![License](http://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat)](LICENSE.md)
[![Codecov](https://img.shields.io/codecov/c/github/tdixon97/TemplateSpecFits.jl?logo=codecov)](https://app.codecov.io/gh/legend-exp/TemplateSpecFits.jl)
[![GitHub issues](https://img.shields.io/github/issues/tdixon97/TemplateSpecFits.jl?logo=github)](https://github.com/tdixon97/TemplateSpecFits.jl/issues)
[![GitHub pull requests](https://img.shields.io/github/issues-pr/tdixon97/TemplateSpecFits.jl?logo=github)](https://github.com/tdixon97/TemplateSpecFits.jl/pulls)
[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit)](https://github.com/pre-commit/pre-commit)


Many applications in experimental physics requiring modelling experimental data with templates, usually based on Monte-Carlo simulations.
This package provides fast, fully customisable, bayesian statistical analysis based on template models and BAT.jl.

In addition, support is given for folding systematic uncertainities directly into the statistical model...


## Statistical model
We support arbitrary binned models. This means the forward model is given by:

$$
\mu_i = \sum_{j=1}^N f_j(\vec{\theta})\, T_j(\vec{\theta})_i
$$

where  $i$ indexes the bins, $j$ indexes the model components, $f_j$ is the normalization factor for the template $T_j$ the value of the $j$-th template in bin $i$.

- $f_j$ can be an arbritary function of the model parameters $\vec{\theta}$
- $T_j$ can also depend on the parameters, this allows for "template-morphing" to handle systematic uncertainities with Interpolations.jl.

In this way it is simple to include additional spectra or multidimensional spectra.
