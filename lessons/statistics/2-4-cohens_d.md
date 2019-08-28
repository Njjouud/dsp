[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)
Since the cohen size is a negative number which will led ti decrease the mean
# Solution goes here
from __future__ import print_function, division

%matplotlib inline
import numpy as np
import nsfg
import first
import thinkplot
preg = nsfg.ReadFemPreg()
live = preg[preg.outcome == 1]
firsts = live[live.birthord == 1]
others = live[live.birthord != 1]
diff = firsts.mean() - others.mean()
var1 = firsts.var()
var2 = others.var()
n1, n2 = len(firsts), len(others)
pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
d = diff / np.sqrt(pooled_var)
d



