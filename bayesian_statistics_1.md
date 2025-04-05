# Bayesian Statistics
Mauricio Matoma

First simulation

``` r
set.seed(20202020)
boxes <- sample(c("GG", "SS","GS"),
                size=10^5, replace = TRUE,
                prob=c(1/3,1/3,1/3))
table(boxes)/10^5
```

    boxes
         GG      GS      SS 
    0.33333 0.33413 0.33254 
