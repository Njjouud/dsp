[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

from __future__ import print_function, division

%matplotlib inline

import numpy as np

import nsfg
import first
import thinkstats2
import thinkplot
resp = nsfg.ReadFemResp()
pmf = thinkstats2.Pmf(resp, label='actual')
new_pmf = pmf.Copy(label='observed')
d=None
for x, p in pmf.Items():
    d=new_pmf.Mult(x, x)
        
thinkplot.PrePlot(2)
thinkplot.Pmfs([pmf, d])
thinkplot.Config(xlabel='Class size', ylabel='PMF')
