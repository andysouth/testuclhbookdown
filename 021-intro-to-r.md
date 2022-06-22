# Course materials

These are the materials for a two day course introducing R and RStudio for UCLH clinicians.    

There are a mixture of slides that will be presented and practical sessions that will be run through.    

In the course we aim to get learners using R and making their first plot at the very start. We will then return to explain more of the concepts later.    

The slides are provided in powerpoint format so that they can be viewed locally (and partly because this was adapted from an earlier course). The slides are actually generated using R from plain text files containing R code.


#### Day 1 {-}

[Welcome]()

* introductions
* brief course objectives
* link to pre-course instructions
* check access to UCLH Data Science Desktop


[1: an R taster](sessions/1-R-taster.pptx)

* introducing RStudio & R and difference between them
* download this project into RStudio
* some necessary setup on UCLH systems


[1.1: R taster script](sessions/1-R-taster-script.R)

* read in a tiny patient dataset from a csv file
* look at the data in R 
* calculate new variables 
* make first plots 


[2: intro to R](sessions/2-R-intro.pptx)

* R, what & why
* R & data in the NHS
* RStudio recap
* R Objects, Functions & Packages
* Vectors
* Data Frames
* Functions
* Packages
* Tidyverse v.brief intro

[todo mention tibble with data frames]

[3: data good practice](sessions/3-data-good-practice.pptx)


* Tidy data
* Data types
* Data good practice
* Example of poorly formatted spreadsheet
[no need to do exercise]
[todo probably replace exercise with something simpler]


[4: getting data into R](sessions/4-read-data.pptx)


* reading a csv into R (CCHIC data)
* file paths [todo replace setwd() with RStudio project terminology]
* viewing data in R

[todo copy cchic data to the book]

#### Day 2 {-}


[5: data visualisation with ggplot2](sessions/5-visualise-data.pptx)

* why visualise ?
* intro to ggplot2
* ggplot2 resources
* ggplot command - aes & geom
* some visualisation tips

[todo add briefly to vis tips]

[5.1: ggplot cchic script](sessions/5-visualise-script-ggplot.R)

* read in cchic csv
* barplots & histograms
* scatterplots
* colour
* facets


[6: data manipulation with dplyr](sessions/6-manipulate-data.pptx)

* dplyr verbs
* pipe
* logical operators
* tidying cchic data
* exercises

[todo add native pipe]







