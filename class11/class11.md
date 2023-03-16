Class 11 Lab Session
================
Olivia Chu

# Section 1. Proportion of G/G in a Population

Download a CSV file from Ensemble \<
https://useast.ensembl.org/Homo_sapiens/Variation/Sample?db=core;r=17:39818860-39938861;v=rs8067378;vdb=variation;vf=105535077#373531_tablePanel
\>

Here, we read this CSV file

``` r
mxl <- read.csv("MXL data.csv")
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
table(mxl$Genotype..forward.strand.) / nrow(mxl) * 100
```


        A|A     A|G     G|A     G|G 
    34.3750 32.8125 18.7500 14.0625 

14% of Mexican Ancestry in Los Angeles sample population (MXL) are
homozygous for the asthma associated SNP (G\|G).

Now, let’s look at a different population. I picked the GBR.

``` r
gbr <- read.csv("GBR data.csv")
```

Find proportion of G\|G.

``` r
round(table(gbr$Genotype..forward.strand.) / nrow(gbr) * 100, 2)
```


      A|A   A|G   G|A   G|G 
    25.27 18.68 26.37 29.67 

This variant that is associated with childhood asthma is more frequent
in GBR population than the MKL population.

Let’s now dig into this further.
