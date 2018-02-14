# simpleDOE
simpleDOE is a simple Python package to help craft a DOE and measure the significance of a test of proportions.
Test of proportions are widely used in marketing such as A/B testing and Test/Control groups.

**simpleDOE** contains these functions:

### Point Estimate Statistic Functions:
  - **prop_test_power(n1, n2, p1, p2, alpha=0.05):**  Returns the power of a test of two proportions. A power equal or higher to 0.8 is usually considered acceptable for a test.
  - **prop_test_pvalue(n1, n2, p1, p2 ,alpha=0.05, tail=1):** Returns the p-value of a Z test of 2 proportions.
  - **prop_test_conf_interval(p, n, alpha=0.05):** Returns the confidence interval for a test of proportions.

### Optimization Functions:
  - **optimal_experiment_test_prop(n, p1, p2, alpha=0.05, power=0.8):** Calculates the optimal sizes for a test given certain parameters.
  - **optimal_experiment_size(n1_ratio, p1, p2, alpha=0.05, power=0.8):** calculates the optimal size for a 2 group test given a desired ratio.
  - **optimal_control_size(test_n, p1, p2, alpha=0.05, power=0.8):** Calculates the minimal size expected for a control population given a test population and expected proportions.

Functions contain documentation and examples, just type the funtion name followed by a "?" or `help(function)` as in standart Python. 

### Examples:
**1. Calculating the Statistical Power of a Test of 2 proportions:**
    
    A marketing manager wants to execute an experiment testing two different 
    emails offering a product. He divides his population in two groups: test1 
    and test2 containing 20000 and 10000 email receivers respectively.
    He expects a response rate of 2% for his test1 and 1.4% for his test2. 
    Is this test significant and does it have significant statistical power?
    
   `prop_test_power(20000, 10000, 0.02, 0.014)`
    - The result is 0.95772126714949513 which is considered an acceptable level 
    of power in this case. The manager can proceed with the experiment.

### Installation:

In a terminal run:
`pip install simpleDOE`

This [link leads you to the package page in pypi](https://pypi.python.org/pypi/simpleDOE/1.0).

To get involved in the project or to report bugs, please reach out to flavio.bossolan@gmail.com.
