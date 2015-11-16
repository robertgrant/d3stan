Stan interactive
================

[Stan](http://mc-stan.org) is a C++ library for probabilistic sampling, with many interfaces allowing applied researchers to fit complex Bayesian models to their data from inside their favourite analysis software. As with any Bayesian simulation, the idea is that successive samples converge to the desired posterior distribution of the parameter(s). But things sometimes go wrong. It's essential to check that the 'chain' of samples has behaved as expected:
* that it has converged to a posterior distribution,
* that autocorrelation is not distorting the distribution, and
* that there are no outlier samples biasing the statistics.

This is usually done by generating diagnostic statistics and plots, excluding badly behaved parts of the chain if you spot a problem, and then doing it again. This can be really time-consuming when there are many parameters, which is why I wrote **stan interactive**. By writing the chains into an interactive web page, we can employ the powerful JavaScript libraries D3, crossfilter and angular to recalculate and draw charts on the fly, freeing up the user to concentrate on what the results mean. You can [view the prototype output here](http://www.robertgrantstats.co.uk/stan-interactive/stan.html).
