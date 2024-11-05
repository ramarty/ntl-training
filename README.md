# Nighttime Lights for Economic Analysis

## Background

This material was developed by the [ieConnect](https://www.worldbank.org/en/about/unit/unit-dec/impactevaluation/partnerships/ieconnect) team as an introduction to using nighttime lights for economic analysis, with a focus on transportation applications.

## Course description

Nighttime lights have become a widely used proxy for local economic activity in the social science literature. [Henderson, Storeygard, and Weil's](https://www.aeaweb.org/articles?id=10.1257/aer.102.2.994) seminal 2012 paper illustrated the use of leveraging nighttime lights to measure growth. Their paper helped launch the use of nighttime lights in a variety of applications; a Google scholar search of ["nighttime lights economics"](https://scholar.google.com/scholar?hl=en&as_sdt=0%2C9&q=nighttime+lights+economics&btnG=) brings over 40,000 responses. During this time, the quality of nighttime lights data has improved and algorithms to process data have also improved. Despite improvements, using nighttime lights requires key considerations of data quality---such as cloud cover masking lights.

This course provides an overview of using nighttime lights data. It covers the different sources of nighttime lights, how to query and aggregate data, and different applications of using the data.

## Prerequisites

The course assumes familiarity with R or Python. For an introduction to these programming languages, see the DIME Analytics [R training](https://github.com/worldbank/dime-r-training) and the DIME Analytics and DECID [Python training](https://github.com/worldbank/dec-python-course).

## Training content

1. [Introduction to Spatial Analysis](https://html-preview.github.io/?url=https://raw.githubusercontent.com/ramarty/ntl-training/refs/heads/main/trainings/01_spatial_analysis_review.html): Provides an overview of working with vector and raster spatial data in R.
2. [Nighttime Lights for Economic Analysis](https://github.com/ramarty/ntl-training/blob/main/trainings/02_into_nighttime_lights.pdf): Provides and overview of nighttime lights datasets and use of nighttime lights for economic and social science analysis.
3. [Nighttime Lights Analysis in R](https://html-preview.github.io/?url=https://raw.githubusercontent.com/ramarty/ntl-training/refs/heads/main/trainings/03_intro_blackmarbler.html): Provides of overview of querying and analyzing nighttime lights data in R, leveraging the [BlackMarbleR](https://worldbank.github.io/blackmarbler/) package.

## NTL Country Diagnostic Code

In addition to providing training content, this repository contains code to quickly (1) produce nighttime lights data for any country (at the ADM0 - ADM3 level, and at the city level) and (2) produces analysis of nighttime lights (e.g., trends and maps).

* [Code](https://github.com/ramarty/ntl-training/blob/main/ntl-diagnostic-code/ntl-diagnostics.qmd)

The top of the code contains required and optional parameters (see below). After entering the parameters, the code can be rendered. The code produces datasets and summary analysis.

```r
# REQUIRED PARAMETERS ----------------------------------------------------------

## File locations
root_dir     <- "~/Desktop"    # Where to put NTL folder
folder_name  <- "NTL Analysis" # The code will create this folder

## Country
iso3_code    <- "PRI"          # ISO3 code for country

## Token
nasa_bearer <- "BEARER-TOKEN"  # NASA Bearer Token

# OPTIONAL PARAMETERS ----------------------------------------------------------

## Months to query
month_start <- "2024-06-01"    # Start month to query 
month_end   <- Sys.Date() %>%  # End month to query
  floor_date(unit = "months") %>% 
  as.character()  

## Years to Query
year_start <- 2012
year_end <- Sys.Date() %>% year()

# Base year for % change maps
pc_base_year <- 2019 
```




