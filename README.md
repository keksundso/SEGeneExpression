# Superenhancer (SE) and their influence on gene expression.
## Method
To quantify the effect of SE on differential gene expression, the β values of the nearest gene was fitted to a linear model (brms (2.10.0) with default priors {Burkner, 2018 #43} and rstan (2.19.2)) (Stan Development Team. 2018. RStan: the R interface to Stan. R package version 2.17.3. http://mc-stan.org). 

    Βg ~ T(ν, μg, σg)  
    μg = α0 + α1 * Enhg  
    σg = γ0 + γ1 * Enhg  

It models the differential gene expression β for a given gene g, by a student-T distribution, defined by ν, μ and σ (degrees of freedom, mean and standard deviation, respectively). The slope α1 can be interpreted as the effect the presence of a SE (Enh = 1), has on the differential gene expression compared to its absence (Enh = 0). The accuracy of the model was tested by a posterior predictive check. 

## Prerequisite
### Software
1. R-libraries defined in the *SuperenhancerGenesAndTheirExpression_bayes.Rmd*.

### Data (can be requested)
1. *sleuth.results.WT.gene_log2FC.csv* Differential gene expression between PC and HC calculated by sleuth. 
2. Table of SE specific for PC, HC and common (calculated with StrandNGS)