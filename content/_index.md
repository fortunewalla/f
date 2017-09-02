---
title: Home
---
<center>
<i class="mega64-octicon octicon-eye"></i> --------------------- <i class="mega64-octicon octicon-eye"></i>

*__tools & techniques for analysis__*
</center>

|   |   |
|---|---|
|<i class="mega64-octicon octicon-hubot"> </i>| __ml__ machine learning, data mining, deep learning, ai| 
|<i class="mega64-octicon octicon-graph"></i>| __da__ probability, statistics, data analysis, business intellligence|
|<i class="fa fa-pencil fa-4x"></i>| __nt__ notes, tips, tricks, usage of tools|
|<i class="mega64-octicon octicon-pulse"></i>| __ts__ time series, signal processing|
|<i class="fa fa-book fa-4x"></i>| __bk__ books, course notes, reference material|
|<i class="mega64-octicon octicon-telescope"></i>| __bz__ project, management, retail, customer, marketing, business|
|<i class="mega64-octicon octicon-beaker"></i>| __cd__ code, experiments, algorithms, software|
|<i class="mega64-octicon octicon-microscope"></i>| __cs__ case studies|
|<i class="fa fa-graduation-cap fa-4x"></i>| __ac__ academics, articles, research papers|

__Syntax highlight test__

```r
# Goal: Some of the standard tests

# A classical setting --
x <- runif(100, 0, 10)                  # 100 draws from U(0,10)
y <- 2 + 3*x + rnorm(100)               # beta = [2, 3] and sigma is 1
d <- lm(y ~ x)
# CLS results --
summary(d)

library(sandwich)
library(lmtest)
# Durbin-Watson test --
dwtest(d, alternative="two.sided")
# Breusch-Pagan test --
bptest(d)
# Heteroscedasticity and autocorrelation consistent (HAC) tests
coeftest(d, vcov=kernHAC)

# Tranplant the HAC values back in --
library(xtable)
sum.d <- summary(d)
xtable(sum.d)
sum.d$coefficients[1:2,1:4] <- coeftest(d, vcov=kernHAC)[1:2,1:4]
xtable(sum.d)
```


__Latex test:__

`$${\sqrt {n}}\left(\left({\frac {1}{n}}\sum _{i=1}^{n}X_{i}\right)-\mu \right)\ {\xrightarrow {d}}\ N\left(0,\sigma ^{2}\right)$$`


