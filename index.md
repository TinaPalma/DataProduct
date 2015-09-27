---
title       : Course Project Power and Sample Size
subtitle    : Your Reproducible Pitch Presentation (27.09.2015)
author      : Tina
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax]     # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## The data
Gathering data is not an easy task and you require to have the right amount. If the sample is too smal then your results are not very accurate enough but on the other hand if it is too large you can spend much time on that. This little application can tell you how much data you need to be sure about your results.
We both know that to make sound decisions based on statistical analysis, you need to be sure you can trust your results. 


## What is the power?
The probability of not committing a Type II error is called the power of a hypothesis test.

Effect Size
To compute the power of the test, one offers an alternative view about the "true" value of the population parameter, assuming that the null hypothesis is false. The effect size is the difference between the true value and the value specified in the null hypothesis.

Effect size = True value - Hypothesized value

--- .class #id 

## T Distribution
Calculating the power when using a t-test is similar to using a normal distribution. As I am assuming to work with a sample standard deviation, I would rather use the t-distribution. 


```r
pwrTest <- pwr.t.test(d = d, power = input$power, sig.level = 0.05,type="one.sample",alternative=input$var )
```
The probability that we make a type II error is 1 - power of the test = 10% (in this case)

--- .class #id 

## How does the application work?
By the default some figures are already set.
You can modify it by changing: 
* 1. First of all,test either greater or two.sided
* 2. The Null hypothesis and the alternative hypothesis
* 3. The desired power and the standard deviation
* 4. and finally ... Submit

--- .class #id 

## Example

onesamplemeans test=t 
Test: greater
H0: 850
HA: 810
Power: 0.9
Standard deviation: 50



```r
delta <- (850-810)/50 
power <-0.9
pwrTest <- pwr.t.test(d = delta, power = power, sig.level = 0.05,type="one.sample",alternative="greater" )
pwrTest
```

```
## 
##      One-sample t test power calculation 
## 
##               n = 14.84346
##               d = 0.8
##       sig.level = 0.05
##           power = 0.9
##     alternative = greater
```

Thank You!
