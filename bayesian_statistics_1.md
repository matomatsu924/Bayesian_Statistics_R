# Bayesian Statistics
Mauricio Matoma

My first simulation

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

Each box appears with about 1/3 probability as expected. Now, let’s
simulate what dagger they will see first.

``` r
dagger <- rbinom(10^5, size = 1, prob=c(1,.5,0)[as.numeric(as.factor(boxes))])
```

The elements of the vector ‘dagger’ take the value of ‘0’ for silver and
‘1’ for gold. The probability of golden dagger depends on the box. If
you are unsure about any piece of the code, go deeper. Check:

``` r
boxes[1:5]#Factores de ejemplo (contenido de cajas)
```

    [1] "GG" "SS" "SS" "GS" "GG"

``` r
as.factor(boxes)[1:5] #Levels de esas cajas
```

    [1] GG SS SS GS GG
    Levels: GG GS SS

``` r
as.numeric(as.factor(boxes)[1:5]) #Convertilas en valores numéricos ("discretos")
```

    [1] 1 3 3 2 1

``` r
c(1,.5,0)[as.numeric(as.factor(boxes))[1:5]] #Los convierte en numéricos "continuos" (probabilidad)
```

    [1] 1.0 0.0 0.0 0.5 1.0

and see what changes.

What is the frequency distribution of ones (gold dagger seen first) and
zeroes (silver dagger seen first)?

``` r
table(dagger)/10^5
```

    dagger
         0      1 
    0.5001 0.4999 

Pretty much 50/50. As expected.

Final Final
