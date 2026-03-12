# Class 12 Lab
Kiana Bohanon (A17802316)

- [Section 1. Proportion of G/G in a
  Population](#section-1-proportion-of-gg-in-a-population)
- [Section 4: Population Scale Analysis
  \[HOMEWORK\]](#section-4-population-scale-analysis-homework)

## Section 1. Proportion of G/G in a Population

Downloaded a CSV file from Ensemble \<
https://useast.ensembl.org/Homo_sapiens/Variation/Sample?db=core;r=17:39835095-39955096;v=rs8067378;vdb=variation;vf=959672880;sample=
\>

Here we read this CSV file:

``` r
mxl <- read.csv("373531-SampleGenotypes-Homo_sapiens_Variation_Sample_rs8067378.csv")
head(mxl)
```

      Sample..Male.Female.Unknown. Genotype..forward.strand. Population.s. Father
    1                  NA19648 (F)                       A|A ALL, AMR, MXL      -
    2                  NA19649 (M)                       G|G ALL, AMR, MXL      -
    3                  NA19651 (F)                       A|A ALL, AMR, MXL      -
    4                  NA19652 (M)                       G|G ALL, AMR, MXL      -
    5                  NA19654 (F)                       G|G ALL, AMR, MXL      -
    6                  NA19655 (M)                       A|G ALL, AMR, MXL      -
      Mother
    1      -
    2      -
    3      -
    4      -
    5      -
    6      -

``` r
table(mxl$Genotype..forward.strand.)
```


    A|A A|G G|A G|G 
     22  21  12   9 

``` r
table(mxl$Genotype..forward.strand.) /nrow(mxl)
```


         A|A      A|G      G|A      G|G 
    0.343750 0.328125 0.187500 0.140625 

## Section 4: Population Scale Analysis \[HOMEWORK\]

One sample is obviously not enough to know what is happening in a
population. You are interested in assessing genetic differences on a
population scale. So, you processed about ~230 samples and did the
normalization on a genome level. Now, you want to find whether there is
any association of the 4 asthma-associated SNPs (rs8067378…) on ORMDL3
expression.

How many samples do we have?

> Q13: Read this file into R and determine the sample size for each
> genotype and their corresponding median expression levels for each of
> these genotypes.

``` r
expr <- read.table("rs8067378_ENSG00000172057.6.txt")
head(expr)
```

       sample geno      exp
    1 HG00367  A/G 28.96038
    2 NA20768  A/G 20.24449
    3 HG00361  A/A 31.32628
    4 HG00135  A/A 34.11169
    5 NA18870  G/G 18.25141
    6 NA11993  A/A 32.89721

``` r
nrow(expr)
```

    [1] 462

Sample size for each genotype:

``` r
table(expr$geno)
```


    A/A A/G G/G 
    108 233 121 

There are 108 A/A, 233 A/G, and 121 G/G.

Median expression levels for each genotype:

``` r
tapply(expr$exp, expr$geno, median, na.rm=TRUE)
```

         A/A      A/G      G/G 
    31.24847 25.06486 20.07363 

For A/A, the median expression level is 31.24. For A/G, it is 25. For
G/G, it is 20.

Lets make a boxplot:

``` r
library(ggplot2)
```

> Q14: Generate a boxplot with a box per genotype, what could you infer
> from the relative expression value between A/A and G/G displayed in
> this plot? Does the SNP effect the expression of ORMDL3? Hint: An
> example boxplot is provided overleaf – yours does not need to be as
> polished as this one.

``` r
ggplot(expr) + aes(x=geno, y=exp, fill=geno) +geom_boxplot(notch=TRUE)
```

![](class12lab_files/figure-commonmark/unnamed-chunk-9-1.png)

Based on this plot, you can infer that there is a difference between the
A/A and G/G relative expression value. So the SNP does effect the
expression of ORMDL3, because if you have the G/G genotype, you are more
likely to see reduced expression.
