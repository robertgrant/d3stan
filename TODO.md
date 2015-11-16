To do
=====

General points:
* There are too many global namespace variables, but once this is fully functioning and stable, it can be cleaned up.
* We need to avoid re-rendering and reading the CSV file in order to omit samples or thin them.

With apologies if these notes-to-self make little sense...

* calculate bounds for x-axes in histograms
* include padding around histograms
* calculate and show r hat and effective sample size, DIC, GLR?
* drop-down (angular?) list to choose parameters for chains
  * or show first ten and allow scrolling and ticking, or 'next 10'
* Angular input to:
  * type in parameter lists
  * drop first n samples from data
  * likewise for thinning
  * and excluding chains
* need to display multiple chains - either as superimposed line charts or densities
  * the chains need to turn into nesting (see test-auto.html)
  * then they can be separated for the line chart or combined in the crossfilter
* consider displaying long chain(s) as quantiles within sample index number bands, rather than line chart
  * perhaps there are 100 index bands on the screen
  * the 40-60th centile is the darkest rectangle, then the 25-40 & 60-75, etc.
* consider an index histogram in the crossfilter with the line chart superimposed
* splines over chains
* How could we read in large chain files efficiently? There could easily be 10e6 samples and 10e4 parameters.
  * One possibility is to have the stan-interactive C++ program chop up the Stan output into a series of csv files, while also writing the names of all the parameters and monitored values into JSON.
  * But also, how should Stan cope with really big output files anyway? They could exceed the maximum file size permitted by the OS.
