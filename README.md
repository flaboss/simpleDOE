# simpleDOE
simpleDOE is a simple Python package to help craft a DOE and measure the significance of a test of proportions.
Test of proportions are widely used in marketing such as A/B testing and Test/Control groups.

simpleDOE contains these functions:
Point Statistic Functions:
  - prop_test_power(n1, n2, p1, p2, alpha=0.05):  Returns the power of a test of two proportions. A power equal or higher to 0.8 is usually considered acceptable for a test.
  - prop_test_pvalue(n1, n2, p1, p2 ,alpha=0.05, tail=1): Returns the p-value of a Z test of 2 proportions.
  - prop_test_conf_interval(p, n, alpha=0.05): Returns the confidence interval for a test of proportions.

Optimization Functions:
  - optimal_experiment_test_prop(n, p1, p2, alpha=0.05, power=0.8): Calculates the optimal sizes for a test given certain parameters.
  - optimal_experiment_size(n1_ratio, p1, p2, alpha=0.05, power=0.8): calculates the optimal size for a 2 group test given a desired ratio.
  - optimal_control_size(test_n, p1, p2, alpha=0.05, power=0.8): Calculates the minimal size expected for a control population given a test population and expected proportions.

Functions contain documentation and examples, just type the funtion name followed by a "?" as in standart Python. 

Installation:
In a terminal run:
pip install simpleDOE

For more, visit the package page.

To get involved in the project, please reach out!
