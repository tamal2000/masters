# Liner Correlation
When is it reasonable to assume a linear relationship between the variable? is `r` significantly different from 0? is p ≠ 0 reasonable?  


A measure of linear relationship is given by the sample linear correlation coefficient r. `r` is an estimate of the population linear correlation coefficient `p`.  
 <img src="https://render.githubusercontent.com/render/math?math=r = \frac{1}{n - 1} \frac{\sum_{i=1}^n (x_i - \overline{x})(y_i - \overline{y})}{s_xs_y} ">  

 Testing, H<sub>0</sub>: p = 0 vs H<sub>1</sub>: p ≠ 0. The test statistic is  <img src="https://render.githubusercontent.com/render/math?math=T_p = \frac{R}{\sqrt{\frac{1 - R^2}{n-2}}} \approx t_{n-2}, under H_0">


# Regression 
**Simple Linear regression:** describe data with a straight line. The data points approximate a straight ine pattern described by  
<center>y = ß<sub>0</sub> + ß<sub>1x</sub> + error<sub>i</sub>.</center>   
Where error term is a random variable (measurement error)

- Different choices of ß<sub>0</sub> and ß<sub>1</sub> gives different models. 
- The target is to minimize error by using this equation:  <img src="https://render.githubusercontent.com/render/math?math=\sum_i(y_i - (b_0 + b_1x_i))^2">  
-  The (fitted) `regression equation` is <img src="https://render.githubusercontent.com/render/math?math=\hat{y}= b_0 + b_1x">, b<sub>0</sub>: intercept, b<sub>1</sub>: slope  
-  least-square approach gives estimates  <img src="https://render.githubusercontent.com/render/math?math=b_1 = r \frac{s_y}{s_x}, b_0 = \overline{y} - b_1\overline{x}">, <img src="https://render.githubusercontent.com/render/math?math=\overline{x}"> is the sample mean of x, s<sub>x</sub> is the sample standard deviation of x. 
-  x: `explanatory variable`
-  y: `response variable`


### Prediction
if there is a liner model than y = b<sub>0</sub> + b<sub>1</sub>x

### When is the linear model appropriate?
- linear equation y = b<sub>0</sub> + b<sub>1</sub>x is a reasonable fit (plot)
- `Coefficient of determination` r<sup>2</sup> is large 
  - <img src="https://render.githubusercontent.com/render/math?math=r^2 = \frac{ExplainedVariation}{TotalVariation}">
  - **0 ≤ r<sup>2</sup> ≤ 1 and if r<sup>2</sup> is “large”** (close to 1), then the linear model is appropriate.
- Linear relationship is significant: test the claim β<sub>1</sub> = 0 against β<sub>1</sub>  ≠ 0.
- Errors should be independent and normally distributed with mean 0 and fixed standard deviation.


#### Testing Linearity: H<sub>0</sub>: ß<sub>1</sub> = 0 vs. H<sub>1</sub>: ß<sub>1</sub> ≠ 0.

<img src="https://render.githubusercontent.com/render/math?math=T_p = \frac{b_1 - \beta_1}{s_{b_1}} \approx t_{n-2}, under H_0">  

- s<sub>b<sub>1</sub></sub> is the standard error, 

#### Hypothesis 
- **Population parameter:** the `slope coefficient` **ß<sub>1</sub>** of the linear regression model 
- **Hypothesis** H<sub>0</sub>:**ß<sub>1</sub>** = 0 vs. H<sub>1</sub> : **ß<sub>1</sub>** ≠ 0,with significance level α=0.01.
- **Data Requirement:** heck requirements using plots: QQ plot of residuals and a “residual plot”
- **Test statistic and P-value or critical region:**  
  <img src="https://render.githubusercontent.com/render/math?math=T_{\Beta} = \frac{b_1}{s_b_1} \approx t_{n-2} under H_0">
- **Conclude:**
  - **Residual:** residual<sub>i</sub> = y<sub>i</sub> - (b<sub>0</sub> + b<sub>1</sub>x<sub>i</sub>)

# Goodness-of-Fit
**Expected frequencies** Expected frequency Ei is the expected number of occurrences of category i in the sample. 

**Hypotheses** 
- H<sub>0</sub>: frequency counts agree with the claimed distribution.   E<sub>i</sub> = n • p<sub>i</sub>
- H<sub>1</sub>: frequency counts do not agree with the claimed distribution. 
**Test Statices** sum of squared and scaled differences. 
<img src="https://render.githubusercontent.com/render/math?math=\sum \frac{(ObservedFrequency - ExpectedFrequency)^2}{Expected Frequency}">, <img src="https://render.githubusercontent.com/render/math?math=X^2 = \sum \frac{(O_i - E_i)^2}{E_i} \approx X_{k-1}^2 under H_0">  
a `chi-square` distribution with k - 1 degrees of freedom. 
**Conclude** H<sub>0</sub> is rejected for `large value` of the observed score X<sup>2</sup>
- **Critical value method:** reject H<sub>0</sub> if X^2 >X<sup>2</sup><sub>k-1, α</sub>
- **P-value method:** reject H<sub>0</sub> if P(X^2 ≥ x^2) < α 

## Chi-square distribution
- parameter: degrees of freedom (df) 
- continuous
- asymmetric: right-skewed
- only positive values

### Hypothesis testing
**Step 0** Indicate population parameter: proportion of ex red, blue, orange  
**Step 1** H<sub>0</sub>: p<sub>1</sub> = 0.13, p<sub>2</sub>: 0.14  
**Step 2** collect data requirements  check  
**Step 4** Testing: <img src="https://render.githubusercontent.com/render/math?math=X^2 = \sum \frac{(O_i - E_i)^2}{E_i} \approx X_{k-1}^2 under H_0">
**Step 5** But H<sub>0</sub> is rejected for large scores of X<sup>2</sup>


#### Contingency Table
A `contingency table` is a table of frequency counts of categorical data corresponding to both variables. 
- **Row Variable:** r categories 
- **Column variable:** c categories 
- in total, r x c cells/entires 
- Example: 
  |            | Left-Handed    |    Right Handed| Total   |
  |------------|:--------------:|:--------------:|--------:|
  |**Male**    |23              |217             |240      |
  |**Female**  |65              |455             |520      |
  |**Total**   |**88**          |**672**         |**760**  |
  

# Independence Test 

Data presentation: a contingency table (or two-way table) is a table of frequency counts of categorical data corresponding to both variables.

**Claim** Gender and left-handedness are dependent.  
**Step 1** 
- H<sub>0</sub>: row and column variable are independent 
- H<sub>1</sub>: row and column variable are dependent 
- significance level = 0.05.
**Step 2** Data requirement check. 
- sample size
- 2 x 2 : all elements > 5
- large table: All E> 1 and 80% of E > 5.  
**Step 3**
<img src="https://render.githubusercontent.com/render/math?math=X^2 = \sum \frac{(O - E)^2}{E} \approx X^2_{(r-1)(c-1)}">  

**Step 4** **H<sub>0</sub>** is rejected for large value of **X<sup>2</sup>**. Compare with critical value X<sup>2</sup><sub>(r-1)(c-1)</sub> or find `P-value` P(X<sup>2</sup> > x<sup>2</sup>) in R. 


<img src="https://render.githubusercontent.com/render/math?math=">
 #
 #
 #
 #
 #
 #
 #
 #
 #
 #
 #
 #
 ##

