Mini Data-Analysis Deliverable 1
================
Sidney S.

# STAT 545A: Mini Data Analysis Project

1.  Load the packages below.

``` r
library(datateachr)
library(tidyverse)
```

    ## ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
    ## ✔ dplyr     1.1.3     ✔ readr     2.1.4
    ## ✔ forcats   1.0.0     ✔ stringr   1.5.0
    ## ✔ ggplot2   3.4.3     ✔ tibble    3.2.1
    ## ✔ lubridate 1.9.2     ✔ tidyr     1.3.0
    ## ✔ purrr     1.0.2     
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()
    ## ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors

1.1 **(1 point)** Out of the 7 datasets available in the `datateachr` package, choose **4** that appeal to you based on their description. Write your choices below:

<!-------------------------- Start your work below ---------------------------->
1: CHOICE\_1\_sample
2: CHOICE\_2\_sample
3: CHOICE\_3\_games
4: CHOICE\_4\_trees
<!----------------------------------------------------------------------------->

1.2 **(6 points)** One way to narrowing down your selection is to *explore* the datasets. Use your knowledge of dplyr to find out at least *3* attributes about each of these datasets (an attribute is something such as number of rows, variables, class type...). The goal here is to have an idea of *what the data looks like*.

*Hint:* This is one of those times when you should think about the cleanliness of your analysis. I added a single code chunk for you below, but do you want to use more than one? Would you like to write more comments outside of the code chunk?

<!-------------------------- Start your work below ---------------------------->
## First explore CHOICE 1 / cancer\_sample

``` r
# The 4 attributes I am most interested in are:
# [1] number of rows 
# [2] number of columns 
# [3] column names / variables in this data set
glimpse(cancer_sample) # There are 569 rows and 32 columns. Variable names (and classes) are also printed in output. 
```

    ## Rows: 569
    ## Columns: 32
    ## $ ID                      <dbl> 842302, 842517, 84300903, 84348301, 84358402, …
    ## $ diagnosis               <chr> "M", "M", "M", "M", "M", "M", "M", "M", "M", "…
    ## $ radius_mean             <dbl> 17.990, 20.570, 19.690, 11.420, 20.290, 12.450…
    ## $ texture_mean            <dbl> 10.38, 17.77, 21.25, 20.38, 14.34, 15.70, 19.9…
    ## $ perimeter_mean          <dbl> 122.80, 132.90, 130.00, 77.58, 135.10, 82.57, …
    ## $ area_mean               <dbl> 1001.0, 1326.0, 1203.0, 386.1, 1297.0, 477.1, …
    ## $ smoothness_mean         <dbl> 0.11840, 0.08474, 0.10960, 0.14250, 0.10030, 0…
    ## $ compactness_mean        <dbl> 0.27760, 0.07864, 0.15990, 0.28390, 0.13280, 0…
    ## $ concavity_mean          <dbl> 0.30010, 0.08690, 0.19740, 0.24140, 0.19800, 0…
    ## $ concave_points_mean     <dbl> 0.14710, 0.07017, 0.12790, 0.10520, 0.10430, 0…
    ## $ symmetry_mean           <dbl> 0.2419, 0.1812, 0.2069, 0.2597, 0.1809, 0.2087…
    ## $ fractal_dimension_mean  <dbl> 0.07871, 0.05667, 0.05999, 0.09744, 0.05883, 0…
    ## $ radius_se               <dbl> 1.0950, 0.5435, 0.7456, 0.4956, 0.7572, 0.3345…
    ## $ texture_se              <dbl> 0.9053, 0.7339, 0.7869, 1.1560, 0.7813, 0.8902…
    ## $ perimeter_se            <dbl> 8.589, 3.398, 4.585, 3.445, 5.438, 2.217, 3.18…
    ## $ area_se                 <dbl> 153.40, 74.08, 94.03, 27.23, 94.44, 27.19, 53.…
    ## $ smoothness_se           <dbl> 0.006399, 0.005225, 0.006150, 0.009110, 0.0114…
    ## $ compactness_se          <dbl> 0.049040, 0.013080, 0.040060, 0.074580, 0.0246…
    ## $ concavity_se            <dbl> 0.05373, 0.01860, 0.03832, 0.05661, 0.05688, 0…
    ## $ concave_points_se       <dbl> 0.015870, 0.013400, 0.020580, 0.018670, 0.0188…
    ## $ symmetry_se             <dbl> 0.03003, 0.01389, 0.02250, 0.05963, 0.01756, 0…
    ## $ fractal_dimension_se    <dbl> 0.006193, 0.003532, 0.004571, 0.009208, 0.0051…
    ## $ radius_worst            <dbl> 25.38, 24.99, 23.57, 14.91, 22.54, 15.47, 22.8…
    ## $ texture_worst           <dbl> 17.33, 23.41, 25.53, 26.50, 16.67, 23.75, 27.6…
    ## $ perimeter_worst         <dbl> 184.60, 158.80, 152.50, 98.87, 152.20, 103.40,…
    ## $ area_worst              <dbl> 2019.0, 1956.0, 1709.0, 567.7, 1575.0, 741.6, …
    ## $ smoothness_worst        <dbl> 0.1622, 0.1238, 0.1444, 0.2098, 0.1374, 0.1791…
    ## $ compactness_worst       <dbl> 0.6656, 0.1866, 0.4245, 0.8663, 0.2050, 0.5249…
    ## $ concavity_worst         <dbl> 0.71190, 0.24160, 0.45040, 0.68690, 0.40000, 0…
    ## $ concave_points_worst    <dbl> 0.26540, 0.18600, 0.24300, 0.25750, 0.16250, 0…
    ## $ symmetry_worst          <dbl> 0.4601, 0.2750, 0.3613, 0.6638, 0.2364, 0.3985…
    ## $ fractal_dimension_worst <dbl> 0.11890, 0.08902, 0.08758, 0.17300, 0.07678, 0…

``` r
# [4] number of distinct sample IDs 
n_distinct(cancer_sample$ID)  # There are 569 distinct cancer sample IDs
```

    ## [1] 569

#### Other exploration /things I want to know beyond the 4 attributes explored with dplyr:

``` r
class(cancer_sample)
```

    ## [1] "spec_tbl_df" "tbl_df"      "tbl"         "data.frame"

``` r
nrow(cancer_sample) - n_distinct(cancer_sample$ID)  # no double IDs
```

    ## [1] 0

``` r
sum(is.na(cancer_sample$ID))  # no data without an associated ID 
```

    ## [1] 0

``` r
sum(is.na(cancer_sample))  # No missing data at all? Fabulous!
```

    ## [1] 0

``` r
# what are the possible sample diagnoses?
unique(cancer_sample$diagnosis) # M for malignant and B for benign I assume.
```

    ## [1] "M" "B"

## Explore CHOICE 2 / flow\_sample

``` r
# The 4 attributes I am most interested in are:
# [1] number of rows 
# [2] number of columns 
# [3] column names / variables in this data set
glimpse(flow_sample) 
```

    ## Rows: 218
    ## Columns: 7
    ## $ station_id   <chr> "05BB001", "05BB001", "05BB001", "05BB001", "05BB001", "0…
    ## $ year         <dbl> 1909, 1910, 1911, 1912, 1913, 1914, 1915, 1916, 1917, 191…
    ## $ extreme_type <chr> "maximum", "maximum", "maximum", "maximum", "maximum", "m…
    ## $ month        <dbl> 7, 6, 6, 8, 6, 6, 6, 6, 6, 6, 6, 7, 6, 6, 6, 7, 5, 7, 6, …
    ## $ day          <dbl> 7, 12, 14, 25, 11, 18, 27, 20, 17, 15, 22, 3, 9, 5, 14, 5…
    ## $ flow         <dbl> 314, 230, 264, 174, 232, 214, 236, 309, 174, 345, 185, 24…
    ## $ sym          <chr> NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, N…

``` r
# There are 218 rows and 7 columns. Variable names (and classes) are also printed in output. 

# [4] number of distinct station IDs 
n_distinct(flow_sample$station_id) 
```

    ## [1] 1

``` r
# There is only one station ID (all of this data is from a simgle station ?) 
```

#### Other exploration /things I want to know beyond the 4 attributes explored with dplyr:

``` r
class(flow_sample)
```

    ## [1] "tbl_df"     "tbl"        "data.frame"

``` r
sum(is.na(flow_sample)) # There are 125 missing data points 
```

    ## [1] 125

``` r
sum(is.na(flow_sample$sym)) # and most of them are in the "sym" variable
```

    ## [1] 119

``` r
# where are the other mising data points?
colSums(is.na(flow_sample))
```

    ##   station_id         year extreme_type        month          day         flow 
    ##            0            0            0            2            2            2 
    ##          sym 
    ##          119

``` r
# also try to figure out what column 'sym' is by the data it holds:
unique(flow_sample$sym) # I still don't know what 'sym' is.. 
```

    ## [1] NA  "E" "A" "B"

## Explore CHOICE 3/ steam\_games

``` r
# The 4 attributes I am most interested in are:
# [1] number of rows 
# [2] number of columns 
# [3] column names / variables in this data set
glimpse(steam_games) # There are 40,833 rows and 21 columns. Variable names (and classes - mostly character here) are also printed in output. 
```

    ## Rows: 40,833
    ## Columns: 21
    ## $ id                       <dbl> 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14…
    ## $ url                      <chr> "https://store.steampowered.com/app/379720/DO…
    ## $ types                    <chr> "app", "app", "app", "app", "app", "bundle", …
    ## $ name                     <chr> "DOOM", "PLAYERUNKNOWN'S BATTLEGROUNDS", "BAT…
    ## $ desc_snippet             <chr> "Now includes all three premium DLC packs (Un…
    ## $ recent_reviews           <chr> "Very Positive,(554),- 89% of the 554 user re…
    ## $ all_reviews              <chr> "Very Positive,(42,550),- 92% of the 42,550 u…
    ## $ release_date             <chr> "May 12, 2016", "Dec 21, 2017", "Apr 24, 2018…
    ## $ developer                <chr> "id Software", "PUBG Corporation", "Harebrain…
    ## $ publisher                <chr> "Bethesda Softworks,Bethesda Softworks", "PUB…
    ## $ popular_tags             <chr> "FPS,Gore,Action,Demons,Shooter,First-Person,…
    ## $ game_details             <chr> "Single-player,Multi-player,Co-op,Steam Achie…
    ## $ languages                <chr> "English,French,Italian,German,Spanish - Spai…
    ## $ achievements             <dbl> 54, 37, 128, NA, NA, NA, 51, 55, 34, 43, 72, …
    ## $ genre                    <chr> "Action", "Action,Adventure,Massively Multipl…
    ## $ game_description         <chr> "About This Game Developed by id software, th…
    ## $ mature_content           <chr> NA, "Mature Content Description  The develope…
    ## $ minimum_requirements     <chr> "Minimum:,OS:,Windows 7/8.1/10 (64-bit versio…
    ## $ recommended_requirements <chr> "Recommended:,OS:,Windows 7/8.1/10 (64-bit ve…
    ## $ original_price           <dbl> 19.99, 29.99, 39.99, 44.99, 0.00, NA, 59.99, …
    ## $ discount_price           <dbl> 14.99, NA, NA, NA, NA, 35.18, 70.42, 17.58, N…

``` r
# [4] number of distinct IDs (for games)
n_distinct(steam_games$id) #40833
```

    ## [1] 40833

#### Other exploration /things I want to know beyond the 4 attributes explored with dplyr:

``` r
class(steam_games)
```

    ## [1] "spec_tbl_df" "tbl_df"      "tbl"         "data.frame"

``` r
nrow(steam_games) - n_distinct(steam_games$id) # no double game ids - good
```

    ## [1] 0

``` r
sum(is.na(steam_games$id)) # just checking one of the unique ids isn't 'NA'
```

    ## [1] 0

``` r
sum(is.na(steam_games))#  180899 is a lot of missing data 
```

    ## [1] 180899

``` r
# look to see where (in which variable) the data are missing:
colSums(is.na(steam_games))
```

    ##                       id                      url                    types 
    ##                        0                        0                        2 
    ##                     name             desc_snippet           recent_reviews 
    ##                        2                       41                    35317 
    ##              all_reviews             release_date                developer 
    ##                     9553                        2                      342 
    ##                publisher             popular_tags             game_details 
    ##                     5100                      135                      520 
    ##                languages             achievements                    genre 
    ##                       36                    28639                      438 
    ##         game_description           mature_content     minimum_requirements 
    ##                      103                    35126                    16953 
    ## recommended_requirements           original_price           discount_price 
    ##                    16947                     5353                    26290

``` r
# so almost everywhere
```

## Explore CHOICE 4/ vancouver\_trees

``` r
# The 4 attributes I am most interested in are:
# [1] number of rows 
# [2] number of columns 
# [3] column names / variables in this data set
glimpse(vancouver_trees)
```

    ## Rows: 146,611
    ## Columns: 20
    ## $ tree_id            <dbl> 149556, 149563, 149579, 149590, 149604, 149616, 149…
    ## $ civic_number       <dbl> 494, 450, 4994, 858, 5032, 585, 4909, 4925, 4969, 7…
    ## $ std_street         <chr> "W 58TH AV", "W 58TH AV", "WINDSOR ST", "E 39TH AV"…
    ## $ genus_name         <chr> "ULMUS", "ZELKOVA", "STYRAX", "FRAXINUS", "ACER", "…
    ## $ species_name       <chr> "AMERICANA", "SERRATA", "JAPONICA", "AMERICANA", "C…
    ## $ cultivar_name      <chr> "BRANDON", NA, NA, "AUTUMN APPLAUSE", NA, "CHANTICL…
    ## $ common_name        <chr> "BRANDON ELM", "JAPANESE ZELKOVA", "JAPANESE SNOWBE…
    ## $ assigned           <chr> "N", "N", "N", "Y", "N", "N", "N", "N", "N", "N", "…
    ## $ root_barrier       <chr> "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "…
    ## $ plant_area         <chr> "N", "N", "4", "4", "4", "B", "6", "6", "3", "3", "…
    ## $ on_street_block    <dbl> 400, 400, 4900, 800, 5000, 500, 4900, 4900, 4900, 7…
    ## $ on_street          <chr> "W 58TH AV", "W 58TH AV", "WINDSOR ST", "E 39TH AV"…
    ## $ neighbourhood_name <chr> "MARPOLE", "MARPOLE", "KENSINGTON-CEDAR COTTAGE", "…
    ## $ street_side_name   <chr> "EVEN", "EVEN", "EVEN", "EVEN", "EVEN", "ODD", "ODD…
    ## $ height_range_id    <dbl> 2, 4, 3, 4, 2, 2, 3, 3, 2, 2, 2, 5, 3, 2, 2, 2, 2, …
    ## $ diameter           <dbl> 10.00, 10.00, 4.00, 18.00, 9.00, 5.00, 15.00, 14.00…
    ## $ curb               <chr> "N", "N", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "…
    ## $ date_planted       <date> 1999-01-13, 1996-05-31, 1993-11-22, 1996-04-29, 19…
    ## $ longitude          <dbl> -123.1161, -123.1147, -123.0846, -123.0870, -123.08…
    ## $ latitude           <dbl> 49.21776, 49.21776, 49.23938, 49.23469, 49.23894, 4…

``` r
# There are 146,611 rows and 20 columns. Variable names (and classes) are also printed in output. 

# [4] number of distinct tree ids
n_distinct(vancouver_trees$tree_id) 
```

    ## [1] 146611

``` r
# 146611
```

#### Other exploration /things I want to know beyond the 4 attributes explored with dplyr:

``` r
class(vancouver_trees)
```

    ## [1] "tbl_df"     "tbl"        "data.frame"

``` r
nrow(vancouver_trees) - n_distinct(vancouver_trees$tree_id) # no repeat tree IDs - good
```

    ## [1] 0

``` r
sum(is.na(vancouver_trees$tree_id)) # just checking one of the unique Tree ids isn't 'NA'
```

    ## [1] 0

``` r
sum(is.na(vancouver_trees))# 191135
```

    ## [1] 191135

``` r
# Where are the data missing?
colSums(is.na(vancouver_trees)) 
```

    ##            tree_id       civic_number         std_street         genus_name 
    ##                  0                  0                  0                  0 
    ##       species_name      cultivar_name        common_name           assigned 
    ##                  0              67559                  0                  0 
    ##       root_barrier         plant_area    on_street_block          on_street 
    ##                  0               1486                  0                  0 
    ## neighbourhood_name   street_side_name    height_range_id           diameter 
    ##                  0                  0                  0                  0 
    ##               curb       date_planted          longitude           latitude 
    ##                  0              76548              22771              22771

<!----------------------------------------------------------------------------->
1.3 **(1 point)** Now that you've explored the 4 datasets that you were initially most interested in, let's narrow it down to 1. What lead you to choose this one? Briefly explain your choice below.

<!-------------------------- Start your work below ---------------------------->
### I am choosing the first data set I examined / CHOICE 1: 'cancer\_sample'.

#### Three reasons for my choice:

#### \[1\] This is the only data set with no missing data;

#### \[2\] Most variables are numeric and continous.

#### (Both \[1\] and \[2\] should simplify later analyses.);

#### \[3\] It is health-related and therefore the most interesting to me.

<!----------------------------------------------------------------------------->
1.4 **(2 points)** Time for a final decision! Going back to the beginning, it's important to have an *end goal* in mind. For example, if I had chosen the `titanic` dataset for my project, I might've wanted to explore the relationship between survival and other variables. Try to think of 1 research question that you would want to answer with your dataset. Note it down below.

<!-------------------------- Start your work below ---------------------------->
#### MAIN REASEARCH QUESTION: Do malignant versus benign tumours differ in their radius (radius\_mean) and/or concavity (concavity\_mean)?

#### NB: I am assuiming that for: 'cancer\_sample$diagnosis', "M"= malignant and "B"= benign

<!----------------------------------------------------------------------------->
# Task 2: Exploring your dataset

If we rewind and go back to the learning objectives, you'll see that by the end of this deliverable, you should have formulated *4* research questions about your data that you may want to answer during your project. However, it may be handy to do some more exploration on your dataset of choice before creating these questions - by looking at the data, you may get more ideas. **Before you start this task, read all instructions carefully until you reach START HERE under Task 3**.

2.1 **(12 points)** Complete *4 out of the following 8 exercises* to dive deeper into your data. All datasets are different and therefore, not all of these tasks may make sense for your data - which is why you should only answer *4*.

Make sure that you're using dplyr and ggplot2 rather than base R for this task. Outside of this project, you may find that you prefer using base R functions for certain tasks, and that's just fine! But part of this project is for you to practice the tools we learned in class, which is dplyr and ggplot2.

1.  Plot the distribution of a numeric variable.
2.  Create a new variable based on other variables in your data (only if it makes sense)
3.  Investigate how many missing values there are per variable. Can you find a way to plot this?
4.  Explore the relationship between 2 variables in a plot.
5.  Filter observations in your data according to your own criteria. Think of what you'd like to explore - again, if this was the `titanic` dataset, I may want to narrow my search down to passengers born in a particular year...
6.  Use a boxplot to look at the frequency of different observations within a single variable. You can do this for more than one variable if you wish!
7.  Make a new tibble with a subset of your data, with variables and observations that you are interested in exploring.
8.  Use a density plot to explore any of your variables (that are suitable for this type of plot).

2.2 **(4 points)** For each of the 4 exercises that you complete, provide a *brief explanation* of why you chose that exercise in relation to your data (in other words, why does it make sense to do that?), and sufficient comments for a reader to understand your reasoning and code.

<!-------------------------- Start your work below ---------------------------->
## 1. Plot the distribution of a numeric variable.

I am going to plot the distribution of: cancer\_sample$radius\_mean because I want to ensure there is some varaiation in the radii of the samples - otherwise we may not be able to detect a difference in radius between malignant and benign tumours

``` r
ggplot(dat=cancer_sample, aes(x=radius_mean)) +
  geom_histogram(colour = "blue") +
  labs(x = "Radius of Cancer Sample", title = "Distribution of Cancer Sample Radii")
```

    ## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.

![](SaintMDA1_files/figure-markdown_github/distribution-1.png)

COMMENT(S): This looks basically normally distributed (and variable). 0 concerns.

## 5. Filter observations in your data according to your own criteria.

Let's filter out observations to check that the radii data of malignant tumours is still normally distributed (because it is conceivable that malignant tumours are progressed and abnormal, so let's just see what the radii of the more severe cancer samples look like)

``` r
#filter
malignant_cancer_samples <- cancer_sample %>% 
  filter(diagnosis=="M")


# the next step, not an explicit part of this exercise, is to remake the histogram of cancer sample radii within malignant samples: #plot:
ggplot(dat=malignant_cancer_samples, aes(x=radius_mean)) +
  geom_histogram(colour = "red") +
  labs(x = "Radius of Cancer Sample", title = "Distribution of Malignant Cancer Sample Radii")
```

    ## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.

![](SaintMDA1_files/figure-markdown_github/filter-1.png)

COMMENT(S): Good thing I checked - this almost looks like a bimodal distribution. I may need to return to this later, or at least keep this in mind while I try to answer my research question.

## 8. Use a density plot to explore any of your variables (that are suitable for this type of plot).

If we smooth the malignant cancer radii data via density plot, does it still look bimodal?

``` r
cancer_sample %>%
  filter(diagnosis=="M") %>%
  ggplot(aes(x=radius_mean)) +
    geom_density(alpha=0.5) +
    labs(x = "Radius of Cancer Sample", title = "Density Distribution of Malignant Cancer Sample Radii")
```

![](SaintMDA1_files/figure-markdown_github/densityplot-1.png)

COMMENT(S): Yikes - these data look bimodal.

## 7. Make a new tibble with a subset of your data, with variables and observations that you are interested in exploring.

Recall that my research question is: Do malignant versus benign tumours differ in their radius (radius\_mean) and/or concavity (concavity\_mean)? - so I am goint to select the hypothesize predictor: (diagnosis), and dependent variables (radius\_mean and concavity\_mean):

``` r
cancer_sample_desired_vars <- cancer_sample %>%
  select(ID, diagnosis, radius_mean, concavity_mean) 

# and make sure it is a tibble
cancer_sample_desired_vars <- as_tibble(cancer_sample_desired_vars)

# now the data frame with the desired variables looks like:
head(cancer_sample_desired_vars)
```

    ## # A tibble: 6 × 4
    ##         ID diagnosis radius_mean concavity_mean
    ##      <dbl> <chr>           <dbl>          <dbl>
    ## 1   842302 M                18.0         0.300 
    ## 2   842517 M                20.6         0.0869
    ## 3 84300903 M                19.7         0.197 
    ## 4 84348301 M                11.4         0.241 
    ## 5 84358402 M                20.3         0.198 
    ## 6   843786 M                12.4         0.158

``` r
# Aside: note that I have already checked for any missing data in these variables and there is none. 
```

<!----------------------------------------------------------------------------->
# Task 3: Choose research questions

**(4 points)** So far, you have chosen a dataset and gotten familiar with it through exploring the data. You have also brainstormed one research question that interested you (Task 1.4). Now it's time to pick 4 research questions that you would like to explore in Milestone 2! Write the 4 questions and any additional comments below.

<!--- *****START HERE***** --->
### 4 Research Questions:

#### \[1\] MAIN REASEARCH QUESTION: Do malignant versus benign tumours differ in their radius (radius\_mean) and/or concavity (concavity\_mean)?

#### \[2\] follow-up research question 1: if so, by how much?

#### \[3\] follow-up research question 2: can we use tumour radius and/or concavity to predict the diagnosis?

#### \[4\] Related: Are sample concavity and radius related? (amongst both benign and malignant tumours?)

<!----------------------------->
### Attribution

Thanks to Icíar Fernández Boyano for mostly putting this together, and Vincenzo Coia for launching.
