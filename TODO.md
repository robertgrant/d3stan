To do
=====

* need controls for thinning and discarding early samples
* need to display multiple chains - either as superimposed line charts or densities
  * the chains need to turn into nesting (see test-auto.html)
  * then they can be separated for the line chart or combined in the crossfilter
* display chain(s) as quantiles within sample index number bands
  * perhaps there are 100 index bands on the screen
  * the 40-60th centile is the darkest rectangle, then the 25-40 & 60-75, etc.
* calculate and show r hat and effective sample size, DIC, GLR?
* splines over chains
* drop-down (angular?) list to choose parameters for chains
  * or show first ten and allow scrolling and ticking, or 'next 10'
* Angular input to:
  * drop first n samples from data
  * likewise for thinning
  * and excluding chains
* How could we read in large chain files efficiently? There could easily be 10e6 samples and 10e4 parameters.
  * One possibility is to have the stan-interactive C++ program chop up the Stan output into a series of csv files, while also writing the names of all the parameters and monitored values into JSON.
  * But also, how does Stan cope with really big output files anyway? They could exceed the maximum file size permitted by the OS.
