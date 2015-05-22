---
title       : Staistical Power
subtitle    : A shiny app to calculate required sample size
author      : Ian Meikle
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Statistical Power Definition

Type 2 errors occur when the we fail to reject the null hypothesis when it is 
incorrect.

Statistical power is a measure of how likely we are to make a Type 2 error:

$$\Large power = P(reject {\it H}_0 | {\it H}_1 true) $$

---

## Power of t-Test

The R function power.t.test can be used to determine the minimum sample size 
required to avoid a Type 2 error for a specified power level:


```r
power.t.test(power = 0.4, delta = 2, sd = 2)$n
```

```
## [1] 6.900428
```

The default significance level is 95% two-sided, for two samples.

Here delta is the difference ${\it H}_1 - {\it H}_0$.

---

## Shiny App

The Shiny app developed to calculate sample size for a specific power setting is 
[here](http://imeikle.shinyapps.io/app-1/)

The value of ${\it H}_0$ is set at 30.

---

## Possible improvements to the app

The app could be improved by:
* Performing error checking on the inputs
* Allowing the user to choose other parameters to power.t.test, e.g.
    + type of t-test: one-sided or two-sided
    + significance level
    + alternative: one-sample, two-sample or paired
