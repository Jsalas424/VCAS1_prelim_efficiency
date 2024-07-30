---
title: "Descriptive Statistics"
author: "Jonathan Salas"
date: "Last Updated 30 July, 2024"
output: 
  html_document: 
    df_print: kable
    fig_height: 6
    keep_md: true
---



# Import - Point to the correct raw data directory



# Aesthetics



## load Subject Data


# Descriptive Statistics

Analysis Plan:
- histoplots of continuous variables - as of 7/30/24 this was useless to do, shows nothing at all due to small sample
- loess plots of continuous variables; x-axis is each procedure aligned in termporal order
- box plots
- we do procedure time vs rove time "proc_vs_rove" 

Hypotheses:

1) rove_per_app and rove_vs_proc with x axis as patient number to hopefully show a decreasing trend for both; i.e., you can 
  do lots of applications in a short period of time & ablation time is small relative to procedure time as the physician
  becomes more comfortable with our system

### Make Mapping Data

Make temporary mapping data.



## Procedure Time

#### Line Plot

![](step_3_descriptive_stats_files/figure-html/unnamed-chunk-5-1.png)<!-- -->

#### Box Plots

![](step_3_descriptive_stats_files/figure-html/unnamed-chunk-6-1.png)<!-- -->

## Rove Time

#### Line Plot

![](step_3_descriptive_stats_files/figure-html/unnamed-chunk-7-1.png)<!-- -->

#### Box Plots

![](step_3_descriptive_stats_files/figure-html/unnamed-chunk-8-1.png)<!-- -->

# Save Results

# Version and Package Details


```
## [1] "R version 4.4.0 (2024-04-24) Puppy Cup"
```

```
## [1] "RStudio Version 2024.4.2.764 Chocolate Cosmos"
```

<div class="kable-table">

|        |package |loadedversion |
|:-------|:-------|:-------------|
|dplyr   |dplyr   |1.1.4         |
|ggplot2 |ggplot2 |3.5.1         |

</div>

# When were these files last rewritten?


```
## [1] "Tue Jul 30 11:44:30 2024"
```
