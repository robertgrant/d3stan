D3Stan
================

D3Stan is C++ code that takes Stan output files and writes a file that can be opened in a web browser (HTML with CSS and JavaScript) to view the output of the Stan model, interact with and query it, and check that the algorithm has worked as intended. It is like ShinyStan but does not rely on R, and can be used with any Stan interface, or none. It is in C++ so that it can either be a command line tool, or hopefully can be incorporated into core Stan in the future to make interactive output immediately available to all Stan users.

*At present, D3Stan is work in progress. I make no guarantee that it will  work at all until this line is removed from README. I would like to have this done by end of 2019.*

### Viewing the output

### Interacting and querying the model

### Diagnosing algorithm problems

[Stan](http://mc-stan.org) is a C++ library for probabilistic sampling using Markov Chain Monte Carlo (MCMC) algorithms, typically the No U-Turn Sampler (NUTS). There are many interfaces allowing applied researchers to fit complex Bayesian models to their data from inside their favourite analysis software. As with any Bayesian simulation, the idea is that successive samples from the algorithm provide unbiased statistics on the desired posterior distribution of the parameters and other unknown values of interest. But, sometimes things go wrong. It's essential to check that the 'chain' of samples has behaved as expected:
* that it has converged to a posterior distribution,
* that autocorrelation is not distorting the distribution, and
* that there are no outlier samples biasing the statistics.

### Principles
* Try to keep D3.js the only dependency
* This is client side (unless the user puts it on a server)
* The output should be accessible to as many users as possible. It should not require third-party software. It should not require knowledge of HTML/CSS/JS. It should not require the sort of Windows sysadmin approval that trips up a lot of analysts in large organisations, for example working on thin clients. I believe they are best served by a single file containing data, HTML, CSS and JavaScript, even perhaps d3.js itself (licenses permitting...), though this is not standard web dev practice.


### To-do list
* replicate ShinyStan in the first instance (though I reject the trivariate plot; it's just bad dataviz); later, I would combine the two layers of navbar and tabs, and remove duplication of charts.
* Have some threshold number of posterior draws above which we show only summaries like hexbin plots (though the user can override this)
* some kind of parameter chooser GUI, possibly drag-n-drop
* we could add different filters to highlight points on scatterplots
* we could add highlighting in the chainplots too
* we could add more brushing, or interaction with the brushed plots
* we could add more on-click and on-hover info
* we could add help at more places
* we could add links to bring up the manual PDF (at specific sections?)
* maybe there could be an option to plot geodata on a map page (would this need leaflet.js?)
* smoothers over chains
* a neater interface to drop chains, exclude parts of chains, thin chains...
