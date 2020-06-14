# Lecture 4

## General Normal distribution
**z-score of value x:** Let x be a value of interest, related to a population distribution with mean  μ and standard deviation 𝜎. The z-score is,  <sub><img src="https://render.githubusercontent.com/render/math?math=z = \frac{x - \mu}{\sigma} "> </sub>

## The central limit theorem 
Independently draw a sample of size n > 30 from a population with mean μ and standard deviation 𝜎, then <img src="https://render.githubusercontent.com/render/math?math=\overline{X}_n">  has approximately a <img src="https://render.githubusercontent.com/render/math?math=N(\mu, \frac{\sigma^2}{n})"> . Hence standard deviation is <img src="https://render.githubusercontent.com/render/math?math=\frac{\sigma}{\sqrt{n}}">.

## Assessing normality with QQ plot 
 
 A `model distribution` is a probability distribution for describing the `unknown` true population distribution.  
 If a model distribution is used, we say: The `variable` is modelled as a random variable having `model distribution` with `relevant parameter`.  
 ```
 Example: The variable "Birth day - Due day" is a random variable having a normal distribution with mean 0 and standard deviation 10.
 ```
 `Qus:` does this `definition` only works for standard deviations?  
 **Normal QQ-Plot:** Quantile-quantile plot for the dataset x<sub>1</sub>,...,x<sub>n</sub>  

- Ordered values **x<sub>1</sub>,...,x<sub>n</sub>** are plotted against the theoretical quantiles **z<sub>a<sub>1</sub></sub>,...,z<sub>a<sub>n</sub></sub>** of N(0,1). 
- If ploints approximately follow a straight line, then N(μ, 𝜎) is reasonable model distribution. 
- if the straight line is y = a + bx, then μ ≈ a (line's intercept) and 𝜎 ≈ b (line's slope)
- R: qqnorm()

**Note:* Sample size matters**  
`Small n` more variation -> histogram and QQ- plot can deviate a lot from bell shape and straight line respectively even if data comes N(μ, 𝜎<sup>2</sup>).  
`Large n` the histogram and QQ-plot are more reliable.  
  
**Interpret QQ-plot:** For horizontal axis consists of the theoretical quantiles of the standard normal distribution and vertical axis consists of sample quntiles. Draw straight line through middle of the QQ-plot.  
* Points on left side below straight line? left tail of sample is heavier than left tail of N(0,1). 
* Points on left side above Straight line? left trail of (N,1) is heavier than left tail of sample. 
* Poirnt on right side above the straight line? right tail of sample is heavier than right trail of N(0,1). 
* Points on right side below straight line? right trail of N(0,1) is heavier than straight line. 

**Assess Normality of data with QQ-plot**
* make a normal QQ-plot
* if points follow aprox. a straight line y = a + bx (with slop b>0), then N(a,b<sup>2</sub>) is a reasonable as model distribution. 
* if points dont' follow a straight line, then the sample is more like not from a normal distribution. 
  * The sample is most likely from a location-scale family with lighter or heavier tails than those of the normal distribution, depending on the shape of the qq-plot. 

## Sampling distribution of sample mean and sample proportion 

* **Sampling distribution** Let random variable <img src="https://render.githubusercontent.com/render/math?math=\overline{X}_n"> denote the sample means of a sample size n. The sampling distribution of the sample mean consists of all possible values values of <img src="https://render.githubusercontent.com/render/math?math=\overline{X}_n">, based on all possible samples of size n, and corresponding probabilities.  

* **The central limit theorem (CLT):** Independently draw a sample of size n>30 from a population with mean μ and standard deviation 𝜎. Then <img src="https://render.githubusercontent.com/render/math?math=\overline{X}_n">  has approximately a  <sub><img src="https://render.githubusercontent.com/render/math?math=N(\mu, \frac{\sigma}{\sqrt{n}})"></sub>.

f you routinely copy and paste text and other items on your Mac and iOS devices, you will no doubt agree that Apple’s default clipboard features are extremely lacking. Both the iOS and OS X clipboards only allow you to save one clipping at a time. Each clipping you make gets overridden by a new one. As a writer, I rel