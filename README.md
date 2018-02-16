# simpleDOE
simpleDOE is a simple Python package to help craft a DOE and measure the significance of a test of proportions.
Test of proportions are widely used in marketing such as A/B testing and Test/Control groups.

**simpleDOE** contains these functions:

### Point Estimate Statistic Functions:
  - **1. prop_test_power(n1, n2, p1, p2, alpha=0.05):**  Returns the power of a test of two proportions. A power equal or higher to 0.8 is usually considered acceptable for a test.
  
    PARAMETERS:
    - n1 and n2: sizes of groups 1 and 2 used in the test.
    - p1 and p2: proportions being tested related to each group.
    - alpha: desired confidence level. 0.05 is the standard value widely used.
    
  - **2. prop_test_pvalue(n1, n2, p1, p2 ,alpha=0.05, tail=1):** Returns the p-value of a Z test of 2 proportions.
  
    PARAMETERS:
    - n1 and n2: sizes of groups 1 and 2 used in the test.
    - p1 and p2: proportions being tested related to each group.
    - alpha: desired confidence level. 0.05 is the standard value widely used.
    - tail: 1 (default) or 2.
    
  - **3. prop_test_conf_interval(p, n, alpha=0.05):** Returns the confidence interval for a test of proportions.
  
    PARAMETERS:
    - p: Proportion that is the result of the test.
    - n: Total population of the test.
    - alpha: Confidence level (0.05 default).

### Optimization Functions:
  - **4. optimal_experiment_test_prop(n, p1, p2, alpha=0.05, power=0.8):** Calculates the optimal sizes for a test given certain parameters.
  
    PARAMETERS:
    - n: Total available population for a test.
    - p1: Expected proportion of test population 1.
    - p2: Expected proportion of test population 2.
    - alpha: Confidence level of the test (0.05 default).
    - power: Desired power for the test (0.8 default).
    
  - **5. optimal_experiment_size(n1_ratio, p1, p2, alpha=0.05, power=0.8):** calculates the optimal size for a 2 group test given a desired ratio.
  
    PARAMETERS:
    - n1_ratio: % ratio desired for test group 1. Must be between 0 and 1.
    - p1: Expected proportion of test population 1.
    - p2: Expected proportion of test population 2.
    - alpha: Confidence level of the test (0.05 default).
    - power: Desired power for the test (0.8 default).
    
  - **6. optimal_control_size(test_n, p1, p2, alpha=0.05, power=0.8):** Calculates the minimal size expected for a control population given a test population and expected proportions.
  
    PARAMETERS:
    - test_n: Test group population.
    - p1: Expected proportion of test population 1.
    - p2: Expected proportion of test population 2.
    - alpha: Confidence level of the test (0.05 default).
    - power: Desired power for the test (0.8 default).

All functions contain documentation and examples, just type the funtion name followed by a "?" or `help(function)` as in standart Python. 


### Examples:

**Even though the examples below relate to marketing, simpleDOE can also be used in other fields.**


**1. Calculating the Statistical Power of a Test of 2 proportions:**
    
    A marketing manager wants to execute an experiment testing two different 
    emails offering a product. He divides his population in two groups: test1 
    and test2 containing 20000 and 10000 email receivers respectively.
    He expects a response rate of 2% for his test1 and 1.4% for his test2. 
    Is this test significant and does it have significant statistical power?
    
   `prop_test_power(20000, 10000, 0.02, 0.014)`
    - The result is 95% which is considered an acceptable level 
    of power in this case. The manager can proceed with the experiment.
    

**2. Calculating the p-value of a test of 2 proportions:**

    A marketing manager wants to execute an experiment testing two different 
    emails offering a product. He divides his population in two groups: test1 
    and test2 containing 20000 and 10000 email receivers respectively.
    He expects a response rate of 2% for his test1 and 1.4% for his test2. 
    Is this test significant?
    
   `prop_test_pvalue(20000, 10000, 0.02, 0.014)`
    - The result is 0.00011444 which is below the alpha level of the
    test. We consider the test results to be statistically significant.


**3. Calculating the confidence interval of a proportion:**

    A marketing manager ran an experiment that resulted in significant lift
    mailing a population of 50000 customers with an offer. His response rate
    was 3%. What is the confidence interval he can expect if he executes the 
    same experiment?
    
    `prop_test_conf_interval(0.03, 50000)`
   - `[0.0014952354442173917, 0.028504764555782606, 0.031495235444217388]`
    He can expect his results to range from 2.8% and 3.1%


**4. Finding the optimal test sizes:**

    A marketing manager has a population of 50000 people to mail a letter
    with a bonus offer for a marketing experiment. How should he split his 
    test/control groups knowing that he expects a response rate of 3% for his
    test group and 2% for his control based on his past learnings? He wants
    a power of 90% for this experiment.
    
    `optimal_experiment_test_prop(50000, 0.03, 0.02, power=0.9)`
   - `[50000, 46800, 3200, 0.0011871645573293369, 0.9000756458257636]`
    He can divide his experiment in 46800 for test and 3200 as control. This
    way he maximizes his targeting maintaining a considerable holdout for his
    test.


**5. Finding the optimal size for a 2 group test given a desired ratio:**

    A marketing manager wants to know whow many customers he needs to include
    in his next campaigns test/control groups giving the fact that he expects
    a 3% response rate for his test population and 2% for his control population.
    He wants to have a ratio of 70/30 in his test/control group size.
    
    `optimal_experiment_size(0.7, 0.03, 0.02)`
   - `[9819, 6873, 2945, 0.0050851051615335924, 0.8000030155231419]`
    The minimal quantity he needs to have a significant test with a power of 
    at least 0.8 is 6873 for his test group and 2945 for his control group.

**6. Finding the minimal size expected for a control population:**

    A marketing manager will mail a promotion to 20000 customers. Based on his
    experience he expects a response rate of 3% for test and 2% for control. What
    is the minimum control population size he needs if he aims for a test with 90%
    statistical power?
    
    `optimal_control_size(20000, 0.03, 0.02, power=0.9)`
   - `[23411, 20000, 3411, 0.0011878322023432199, 0.90004753759736567]`
    His control size should have at least 3411 customers.


### Installation:

In a terminal run:
`pip install simpleDOE`

This [link leads you to the package page in pypi](https://pypi.python.org/pypi/simpleDOE/1.0).

To get involved in the project or to report bugs, please reach out to flavio.bossolan@gmail.com.
