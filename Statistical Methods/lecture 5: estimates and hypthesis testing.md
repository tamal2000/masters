# Lecture 5: Estimates and Hypothesis testing

## Estimating Population mean  

`Sample mean` is approximately normally distributed. For an this estimator is unbiased: E(X<sub>n</sub>) = µ. 

## Confidence Intervals, CI: 
approximate distribution to construct `confidence intervals`.  

**95% confidence interval:** a confidence interval for µ with confidence level 95% is a range of estimator values, and we are 95% confident that this interval actually contains µ. For 100 independent samples of the same size, construct confidence intervals for each. On average, 95 of them contain μ. **Note:** it does not mean its 95% chance that µ is in this interval.  

## CI for Mean µ: 
How to find 95% confidence interval [a,b]: a and b such that P(a ≤ µ ≤ b) = 0.95. <img src="https://render.githubusercontent.com/render/math?math=Z = \frac{\overline{X - \mu}}{\frac{\sigma}{\sqrt{n}}}">


**Interpretation:** we don't know whether the true µ is in this particular CI or not. if we constructed 100 sample, then approximately 95 event will be present.   
## Statistics for mean µ
if 𝜎 is not known, then sample mean, s<sub>n</sub> is used.   <img src="https://render.githubusercontent.com/render/math?math=Z = \frac{\overline{X - \mu}}{\frac{S_n}{\sqrt{n}}}">

P (a ≤ µ ≤ b), here a and b are the margin of error.  <img src="https://render.githubusercontent.com/render/math?math=E = Z \frac{S_n}{\sqrt{n}}">

## Population for Mean µ
If we know the maximum marginal Error E<sub>Max</sub>, then the sample population must be  <img src="https://render.githubusercontent.com/render/math?math=n \geq (\frac{Z \cdot S_n}{E_{max}})^2">

## Statistics for Population Proportion 

 <img src="https://render.githubusercontent.com/render/math?math=Z = \frac{\hat{P} - p}{\sqrt{\frac{p(1 - p)}{n}}}">

Margin of Error:  <img src="https://render.githubusercontent.com/render/math?math=E = Z \sqrt{\frac{p(1 - p)}{n}}">, where [p<sub>n</sub> - E ≤ p ≤ P<sub>n</sub> + E]


# Hypothesis testing
Five steps of hypothesis testing  
1. Identify population parameter. 
2. Formulate H0 and H1 and choose significance level α
   - present/typical situation is in H0,
   -  hypothesis you wish to reject is in H0,
   - hypothesis you wish to confirm is in H1.
3. Collect data  
    a. Choose test statistic and identify its distribution under H0  
    b. Calculate the value of test statistic based on data  
    c. Find P-value (depending on which alternative):probability under H0 that test statistic has more extreme values than observed value
4. Formulate, based on P-value and α, conclusion regarding H0: reject (small P-value) or not (large P-value)  

**Significance level** 
Denoted by α. Small, usually 0.05, but also 0.01 or 0.1.

**Testing errors**  
Since hypothesis testing is based on data, randomness can cause errors.  
- **Type I error:** mistake of rejecting H<sub>0</sub> when its true. Probability of type I error ≤ α
- **Type II error:** mistake of not rejecting H<sub>0</sub> when its false. its probability: denoted by ß. 
## Proportion 
**Null hypothesis:** **H<sub>0</sub>:** population parameter = hypothetical value  
**Alternant Hypothesis:** **H<sub>1</sub>** Depending on the claim we choose one out of three.  
* Population parameter < hypothetical value  - `left-tailed test`
* Population parameter > hypothetical value  - `right-tailed test`
* Population parameter ≠ hypothetical value  - `two-tailed test`

### Test Statistic Proportion:  
The test statistic is a random variable used for deciding about H<sub>0</sub>. It is found by converting the sample statistic (proportion/mean) with the assumption that H<sub>0</sub> is true.  

Use that the sampling distribution of the sample proportion approximately has a N(p, p(1−p) ) distribution. A good test statistic is  <img src="https://render.githubusercontent.com/render/math?math=Z = \frac{\hat{P} - p}{\sqrt{\frac{p(1 - p)}{n}}}"> where, p is the claimed value. We are interested in the `distribution` of the test statistic under H<sub>0</sub>. 

### Finding P-value 
- **left-tailed:** P -value = area to the left of z 
- **right-tailed:** P -value = area to the right of z 
- **two-tailed & z < 0:** P-value = 2× area to the left of z
- **two-tailed & z > 0:** P-value = 2× area to the right of z

### P-Value and conclusion 
- If P-value ≤ α: reject H0.
- If P-value > α: do not reject H0.  

### Critical region
Fix α and look at the density of the test statistic’s distribution. If the test is 
- **left-tailed:** critical region = extreme left tail
- **two-tailed:** critical region = both extreme left AND right tails
- **right-tailed:** critical region = extreme right tail

## Mean 
**Requirement Check:** 
- The population has a normal distribution, or
- The population has any distribution and n > 30

**Case 1:**  If σ is known (rarely the case), use test statistic, <img src="https://render.githubusercontent.com/render/math?math=Z = \frac{\overline{X - \mu}}{\frac{\sigma}{\sqrt{n}}}">. where μ is the claimed value under H<sub>0</sub>. Under H<sub>0</sub> , Z ∼ N (0, 1) approximately.

**Case 2:** If σ unknown, estimate via sample standard deviation S<sub>n</sub>. <img src="https://render.githubusercontent.com/render/math?math=T = \frac{\overline{X - \mu}}{\frac{S_n}{\sqrt{n}}}">. Under H<sub>0</sub>, T ∼ t<sub>n−1</sub>, a t-distribution with n − 1 degrees of freedom.  
Find t<sub>n−1,α</sub> such that P(T ≥ tn−1,α) = α, where T has a t-distribution with n − 1 degrees of freedom.

### Critical Regions: 
Test with sample size n and significance level α
- **left-tailed test:** critical region to the left of −t<sub>n−1,α</sub>
- **right-tailed test:** critical region to the right of tt<sub>n−1,α</sub>
- **two-tailed test:** critical region to the left of −t<sub>n−1,α/2</sub> and to the right of t<sub>n−1,α/2</sub>  

**Confidence Intervals for μ**
(1 − α) confidence interval (CI) for μ
<img src="https://render.githubusercontent.com/render/math?math=E = t_{n-1,\alpha/2} \frac{s_n}{sqrt{n}}">   

### Two sample problems 

- Two samples are `dependent` if values in one sample are **related** to values in the other sample, or form natural pairs. 
- Two samples are `independent` if there is no **relationship** between two samples. In this case **sample size** are also `independent`. 

## Two Dependent Samples 
### Testing claims about 2 population means

#### Matched Pairs 
- **Null Hypothesis:** H<sub>0</sub>: µ<sub>1</sub> - µ<sub>2</sub> = claimed value. or µ<sub>1</sub> = µ<sub>2</sub>
- **Alternate Hypothesis:** Depending on claim we choose one out of three hypotheses. 
    + µ<sub>1</sub> - µ<sub>2</sub> < claimed value or µ<sub>1</sub> < µ<sub>2</sub>: `left-tailed` test
    + µ<sub>1</sub> - µ<sub>2</sub> > claimed value or µ<sub>1</sub> > µ<sub>2</sub>: `right-tailed` test
    + µ<sub>1</sub> - µ<sub>2</sub> ≠ claimed value or µ<sub>1</sub> ≠ µ<sub>2</sub>: `two-tailed` test
 
- **Find The difference:** for paired samples, we can calculate the differences, D<sub>1</sub> = X<sub>1</sub>-Y<sub>1</sub> ....
- **Test Statistic:** <img src="https://render.githubusercontent.com/render/math?math=T_d = \frac{\overline{D} - (\mu_1 - \mu_2)}{\frac{S_d}{\sqrt{n}}}">
- **Confidence interval:** <img src="https://render.githubusercontent.com/render/math?math=E = t_{n-1,\alpha/2} \frac{S_d}{\sqrt{n}}">


#### Two means Independent Samples  
- **Null Hypothesis:** H<sub>0</sub>: µ<sub>1</sub> - µ<sub>2</sub> = claimed value. or µ<sub>1</sub> = µ<sub>2</sub>
- **Alternate Hypothesis:** Depending on claim we choose one out of three hypotheses. 
    + µ<sub>1</sub> - µ<sub>2</sub> < claimed value or µ<sub>1</sub> < µ<sub>2</sub>: `left-tailed` test
    + µ<sub>1</sub> - µ<sub>2</sub> > claimed value or µ<sub>1</sub> > µ<sub>2</sub>: `right-tailed` test
    + µ<sub>1</sub> - µ<sub>2</sub> ≠ claimed value or µ<sub>1</sub> ≠ µ<sub>2</sub>: `two-tailed` test
 
- **Requirement Check:** Two samples are independent, both samples sizes are larger than 30 and both come from a normal population. 

**σ<sub>1</sub> = σ<sub>2</sub>**
- **Test Statistic:** <img src="https://render.githubusercontent.com/render/math?math=T_d^{eq} = \frac{(\overline{X_1} - \overline{X_2}) - (\mu_1 - \mu_2)}{\sqrt{\frac{S_p^2}{n_1} %2B \frac{S_p^2}{n_2}}}">
- **Confidence interval:** <img src="https://render.githubusercontent.com/render/math?math=E = t_{(n_1+n_2-2,\alpha/2)} \sqrt{s^2_p/n_1 %2B s^2_p/n_2}">
- **Pooled sample variance:** 
<img src="https://render.githubusercontent.com/render/math?math=S_p^2 = \frac{(n_1 - 1)S_1^2 + (n_2 -1)S_2^2}{n_1 + n_2 - 2}">
- Under the null hypothesis T<sub>2</sub><sup>eq</sup> has a t-distribution with n1 + n2 − 2 degrees of freedom. 

**σ<sub>1</sub> ≠ σ<sub>2</sub>**

- **Test Statistic:** <img src="https://render.githubusercontent.com/render/math?math=T_d^{eq} = \frac{(\overline{X_1} - \overline{X_2}) - (\mu_1 - \mu_2)}{\sqrt{\frac{S_1^2}{n_1} %2B \frac{S_2^2}{n_2}}}">

- ~n degrees of freedom: n = min(n<sub>1</sub> -1 , n<sub>2</sub> - 1)
- **Margin of Error:** <img src="https://render.githubusercontent.com/render/math?math=E = \sqrt{(s_1^2/n_1) %2B (s_2^2/n_2)}">


## Two Proportions
- **Hypothesis** 
  - H<sub>0</sub>: p<sub>1</sub> = p<sub>2</sub>  
  - H<sub>1</sub>: 
    -  p<sub>1</sub> < p<sub>2</sub>: `left tailed` test
    -  p<sub>1</sub> > p<sub>2</sub>: `right tailed` test 
    -  p<sub>1</sub> ≠ p<sub>2</sub>: `two-tailed` test
-  **Requirement Check:** both samples are independent, n<sub>1</sub> and n<sub>2</sub> is more than 30 and normally distributed and each sample sample have 5 success and failures.   
- **Test Statistic:** <img src="https://render.githubusercontent.com/render/math?math=Z_p = \frac{\hat{P_1} - \hat{P_2}}{\sqrt{\overline{P}(1 = \overline{P})/n_1 %2B \overline{P}(1-\overline{p})/n_2}} \approx N(0,1) under H_0">
- **pooled sample proportion:** P<sub>1</sub> = X<sub>1</sub>/n<sub>1</sub>, P<sub>2</sub> = X<sub>2</sub>/n<sub>2</sub>. <img src="https://render.githubusercontent.com/render/math?math=\overline{P} = \frac{X_1 %2B X_2}{n_1 %2B n_2}">
- **Margin of Error** <img src="https://render.githubusercontent.com/render/math?math=E = Z_{\alpha/2} \sqrt{\hat{P_1}(1-\hat{p_1})/n_1 %2B \hat{P_2}(1-\hat{p_2})/n_2}">
- **(1 − α) Confidence interval for p1 − p2** [(pˆ1 −pˆ2)−E,(pˆ1 −pˆ2)+E]


## Linear Correlation
**Question w.r.t. population:** is there a relationship between variables x and y?   
**Experiment:** measure the two variables of n subjects.  

Correlation and linear correlation between two variables V1 and V2
- Higher V1 values usually associated with higher V2 values: `positive correlation`
- Higher V1 values usually associated with lower V2 values: `negative correlation`

**Linear correlation:** if correlated and plotted points follow some straight line.  

### Population and sample linear correlation coefficient
- The population linear correlation coefficient is denoted by, `ρ` 
- The sample linear correlation coefficient is denoted by, `r`  
  <img src="https://render.githubusercontent.com/render/math?math=r = \frac{1}{n - 1} \frac{\sum (x_i - \overline{x})(y_i - \overline{y})}{s_xs_y}">

**Interpretation of r:** (−1 ≤ r ≤ 1)  
- r = 1: perfect positive linear relationship; 
- r > 0 : positive linear relationship;
- r ≈ 0: no linear relationship
- r < 0: negative linear relationship 
- r = -1: perfect negative linear relationship

**Hypothesis:** confidence interval for `ρ` or test H<sub>0</sub>: ρ = 0  
**Requirement Check:** points approx on straight line and no outliers. outliers must be removed to avoid error.  
**Test** H<sub>0</sub>:ρ = 0 vs. H<sub>1</sub>:ρ ≠ 0.  
<img src="https://render.githubusercontent.com/render/math?math=T_p = \frac{R}{\sqrt{\frac{1-R^2}{n-2}}} \approx t_{n-2} under H_0">




