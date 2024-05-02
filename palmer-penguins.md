# Presentation on Palmer Penguins

Obi Azubike 2024-05-02

## Seeting up my environment

Notes: setting up my R environment by loading the ‘tidyverse’ and ‘palmerpenguins’ packages

``` r
library(tidyverse)
```

```         
## ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
## ✔ dplyr     1.1.2     ✔ readr     2.1.4
## ✔ forcats   1.0.0     ✔ stringr   1.5.0
## ✔ ggplot2   3.4.2     ✔ tibble    3.2.1
## ✔ lubridate 1.9.2     ✔ tidyr     1.3.0
## ✔ purrr     1.0.1     
## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
## ✖ dplyr::filter() masks stats::filter()
## ✖ dplyr::lag()    masks stats::lag()
## ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors
```

``` r
library(palmerpenguins)
library(ggplot2)
```

## Visualizations

Here we plot flipper length against body mass

``` r
ggplot(data=penguins,aes(x=flipper_length_mm,y=body_mass_g))+
  geom_point(color="purple")
```

![](palmer-penguins_files/figure-gfm/unnamed-chunk-1-1.png)<!-- -->

## Flipper and body mass by species

Here we plot flipper length against body mass and look at the breakdown by species

``` r
ggplot(data=penguins,aes(x=flipper_length_mm,y=body_mass_g))+
  geom_point(aes(shape=species))
```

```         
## Warning: Removed 2 rows containing missing values (`geom_point()`).
```

![](palmer-penguins_files/figure-gfm/unnamed-chunk-2-1.png)<!-- -->

## Flipper and body mass by species and sex

Here, we plot flipper against body mass and look at thr breakdown by species and sex

``` r
ggplot(data=penguins,aes(x=flipper_length_mm,y=body_mass_g))+
  geom_point(aes(color=species,
                 shape=species)) +
  facet_wrap(~sex)
```

```         
## Warning: Removed 2 rows containing missing values (`geom_point()`).
```

![](palmer-penguins_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->
