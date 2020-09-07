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


# Different hypothesis testing 

|Title|Step 0: Indicate population parameter|Step 1: Formulate H<sub>0</sub>, H<sub>1</sub> & α|Step 2: Collect Data (requirement check)|Step 3: Test Statistics    |Step 4: Conclude|
|--|--|--|--|--|--|
|`Proportion` - Single variable|Population proportion `p`|H<sub>0</sub>: p = 0<br/> H<sub>1</sub>: p < 0 or H<sub>1</sub>: p > 0 or H<sub>1</sub>: p ≠ 0 |Z ∼ N (0, 1) approximately. (n > 30, by CLT)<br/>**left-tailed:** P-value = area left of z <br/>**right-tailed:** P-val = area right of z<br/> **two-tailed & z < 0:** P-value = 2× area to the left of z<br/> **two-tailed & z > 0:** P-value = 2× area to the right of z|<img src="https://render.githubusercontent.com/render/math?math=Z = \frac{\hat{P} - p}{\sqrt{\frac{p(1 - p)}{n}}}"><br/><img src="https://render.githubusercontent.com/render/math?math=E = Z \sqrt{\frac{p(1 - p)}{n}}">, where [p<sub>n</sub> - E ≤ p ≤ P<sub>n</sub> + E]|If P-value ≤ α: reject H0<br/>If P-value > α: do not reject H0|
|`Proportion` - Double variable||H<sub>0</sub>: p<sub>1</sub> = p<sub>2</sub><br/>H<sub>1</sub>:<br/>p<sub>1</sub> < p<sub>2</sub>: `left tailed` test<br/>p<sub>1</sub> > p<sub>2</sub>: `right tailed` test<br/>p<sub>1</sub> ≠ p<sub>2</sub>: `two-tailed` test|both samples are independent, n<sub>1</sub> and n<sub>2</sub> is more than 30 and normally distributed and each sample sample have 5 success and failures.|<img src="https://render.githubusercontent.com/render/math?math=Z_p = \frac{\hat{P_1} - \hat{P_2}}{\sqrt{\overline{P}(1 = \overline{P})/n_1 %2B \overline{P}(1-\overline{p})/n_2}} \approx N(0,1) under H_0"><br/>P<sub>1</sub> = X<sub>1</sub>/n<sub>1</sub>, P<sub>2</sub> = X<sub>2</sub>/n<sub>2</sub>. <img src="https://render.githubusercontent.com/render/math?math=\overline{P} = \frac{X_1 %2B X_2}{n_1 %2B n_2}"><br/><img src="https://render.githubusercontent.com/render/math?math=E = Z_{\alpha/2} \sqrt{\hat{P_1}(1-\hat{p_1})/n_1 %2B \hat{P_2}(1-\hat{p_2})/n_2}"><br/>[(pˆ1 −pˆ2)−E,(pˆ1 −pˆ2)+E]||
|`mean` - σ is known|Population mean **µ**|H<sub>0</sub>: µ = 0<br/> H<sub>1</sub>: µ < 0 or H<sub>1</sub>: µ > 0 or H<sub>1</sub>: µ ≠ 0 |The population has a normal distribution,<br>The population has any distribution and n > 30|<img src="https://render.githubusercontent.com/render/math?math=Z = \frac{\overline{X - \mu}}{\frac{\sigma}{\sqrt{n}}}"> <br/><img src="https://render.githubusercontent.com/render/math?math=E = t_{n-1,\alpha/2} \frac{s_n}{\sqrt{n}}">|P-value ≤ α: reject H0<br/>P-value > α: do not reject H0 |
|`mean` - σ is unknown|Population mean **µ**|H<sub>0</sub>: µ = 0<br/> H<sub>1</sub>: µ < 0 or H<sub>1</sub>: µ > 0 or H<sub>1</sub>: µ ≠ 0 |The population has a normal distribution,<br>The population has any distribution and n > 30|estimate via sample S<sub>n</sub>. <img src="https://render.githubusercontent.com/render/math?math=T = \frac{\overline{X - \mu}}{\frac{S_n}{\sqrt{n}}}"> <br/><img src="https://render.githubusercontent.com/render/math?math=E = t_{n-1,\alpha/2} \frac{s_n}{\sqrt{n}}">|Under H<sub>0</sub>, T ∼ t<sub>n−1</sub>, a t-distribution with n − 1 degrees of freedom. Find t<sub>n−1,α</sub> such that P(T ≥ tn−1,α) = α, where T has a t-distribution with n − 1 degrees of freedom.|
|`mean` 2 population means| | **Null Hypothesis:** H<sub>0</sub>: µ<sub>1</sub> µ<sub>2</sub> = claimed value. or µ<sub>1</sub> = µ<sub>2</sub><br/>**Alternate Hypothesis:** Depending on claim we choose one out of three hypotheses.<br/>µ<sub>1</sub> - µ<sub>2</sub> < claimed value or µ<sub>1</sub> < µ<sub>2</sub>: `left-tailed` test<br/>µ<sub>1</sub> - µ<sub>2</sub> > claimed value or µ<sub>1</sub> > µ<sub>2</sub>: `right-tailed` test<br/>µ<sub>1</sub> - µ<sub>2</sub> ≠ claimed value or µ<sub>1</sub> ≠ µ<sub>2</sub>: `two-tailed` test|Dependent variable|**Test Statistic:** <img src="https://render.githubusercontent.com/render/math?math=T_d = \frac{\overline{D} - (\mu_1 - \mu_2)}{\frac{S_d}{\sqrt{n}}}"><br/>**Confidence interval:**<img src="https://render.githubusercontent.com/render/math?math=E = t_{n-1,\alpha/2} \frac{S_d}{\sqrt{n}}"> ||
|`mean` 2 population means|||Independent Variables, two samples more than 30<br/>**σ<sub>1</sub> = σ<sub>2</sub>**|**Test Statistic:** <img src="https://render.githubusercontent.com/render/math?math=T_d^{eq} = \frac{(\overline{X_1} - \overline{X_2}) - (\mu_1 - \mu_2)}{\sqrt{\frac{S_p^2}{n_1} %2B \frac{S_p^2}{n_2}}}"><br/>**Confidence interval:** <img src="https://render.githubusercontent.com/render/math?math=E = t_{(n_1+n_2-2,\alpha/2)} \sqrt{s^2_p/n_1 %2B s^2_p/n_2}"> ||
||||Independent Variables, two samples more than 30<br/>**σ<sub>1</sub> ≠ σ<sub>2</sub>**|**Test Statistic:** <img src="https://render.githubusercontent.com/render/math?math=T_d^{eq} = \frac{(\overline{X_1} - \overline{X_2}) - (\mu_1 - \mu_2)}{\sqrt{\frac{S_1^2}{n_1} %2B \frac{S_2^2}{n_2}}}"><br/>**Confidence interval:** <img src="https://render.githubusercontent.com/render/math?math=E = \sqrt{(s_1^2/n_1) %2B (s_2^2/n_2)}"> ||
|`Linear Correlation`|confidence interval for `ρ`| H<sub>0</sub>:ρ = 0 vs. H<sub>1</sub>:ρ ≠ 0|points approx on straight line and no outliers. outliers must be removed to avoid error.|<img src="https://render.githubusercontent.com/render/math?math=T_p = \frac{R}{\sqrt{\frac{1-R^2}{n-2}}} \approx t_{n-2} under H_0"><img src="https://render.githubusercontent.com/render/math?math=r = \frac{1}{n - 1} \frac{\sum (x_i - \overline{x})(y_i - \overline{y})}{s_xs_y}">|- r = 1: perfect positive linear relationship<br/>r > 0 : positive linear relationship<br/>r ≈ 0: no linear relationship<br/>r < 0: negative linear relationship<br/> r = -1: perfect negative linear relationship | 
|`Liner regression`|The slope coefficient **β<sub>1</sub>** of the linear regression model.| H<sub>0</sub>: ß<sub>1</sub> = 0, H<sub>1</sub>: ß<sub>1</sub> ≠ 0, H<sub>0</sub>: ß<sub>1</sub> = 0 = 0.01  |QQ plot of residuals and a “residual plot”| <img src="https://render.githubusercontent.com/render/math?math=T_{\Beta} = \frac{b_1}{s_b_1} \approx t_{n-2} under H_0">|H<sub>0</sub> rejected: if ß<sub>1</sub> is in the critical region |