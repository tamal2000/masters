# Liner Correlation
When is it reasonable to assume a linear relationship between the variable? is `r` significantly different from 0? is p ≠ 0 reasonable?  


A measure of linear relationship is given by the sample linear correlation coefficient r. `r` is an estimate of the population linear correlation coefficient `p`.  
 <img src="https://render.githubusercontent.com/render/math?math=r = \frac{1}{n - 1} \frac{\sum_{i=1}^n (x_i - \overline{x})(y_i - \overline{y})}{s_xs_y} ">  

 Testing, H<sub>0</sub>: p = 0 vs H<sub>1</sub>: p ≠ 0. The test statistic is  <img src="https://render.githubusercontent.com/render/math?math=T_p = \frac{R}{\sqrt{\frac{1 - R^2}{n-2}}} \approx t_{n-2}, under H_0">


## Regression 
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
  - r<sup>2</sup> = explained variable / total variation 
  - 0 ≤ r<sup>2</sup> ≤ 1 and if r<sup>2</sup> is “large” (close to 1), then the linear model is appropriate.
- Linear relationship is significant: test the claim β<sub>1</sub> = 0 against β<sub>1</sub>  ≠ 0.
- Errors should be independent and normally distributed with mean 0 and fixed standard deviation.


### Testing Linearity: H<sub>0</sub>: ß<sub>1</sub> = 0 vs. H<sub>1</sub>: ß<sub>1</sub> ≠ 0.

<img src="https://render.githubusercontent.com/render/math?math=T_p = \frac{b_1 - \beta_1}{s_{b_1}} \approx t_{n-2}, under H_0">  

- s<sub>b<sub>1</sub></sub> is the standard error, 

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

