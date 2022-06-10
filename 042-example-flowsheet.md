# Flowsheet example

[issues : rows to columns, multiple values per cell, long names, joining ]

Aim : to summarise questionnaire results captured from flowsheets.

A questionnaire where we are expecting one answer per patient for each question.

Starting with two data extractions from Caboodle.

1. Questionaire results from Flowsheets
2. Patient demographics

Patient cohort was defined in the data extraction by clinic codes and Patient Durable Keys.

## Questionaire results from flowsheets

The flowsheet data are extracted in a long format with question identifiers stored in two columns (note that these may be renamed in the sql extraction) :

* **DisplayName** contains the text on the original form    
* **Name** contains an identifier that is shorter    

Values are stored in columns :

* **Value**
* **Unit** optional, may not be specified

It can be useful to widen these data so that each question is stored in its own column and the values per patient are stored in rows.

To do that widening we can use the *pivot_wider* function from dplyr. You need to specify which columns the names, values and identifiers come from.    

You may need to decide whether to use the DisplayName or Name of the FlowsheetRow works better for what you want to do. DisplayName may be too long to provide a good column name, but Name may not give you a clear indication of what the value contains. 




```r
#library(tidyverse)
library(readr)
library(dplyr)
library(tidyr)
```

In this first example, where there is just one answer recorded for each question-patient combination the pivot_wider should work fine.


```r

dfqs <- read_csv("data//qlong1.csv")

knitr::kable(dfqs)
```



| PatientDurableKey|DisplayName                      |Name         |Value |
|-----------------:|:--------------------------------|:------------|:-----|
|                 1|Have you experienced symptom A ? |symptom A    |no    |
|                 2|Have you experienced symptom A ? |symptom A    |yes   |
|                 1|Do you have family in UK ?       |family in UK |yes   |
|                 2|Do you have family in UK ?       |family in UK |no    |


```r
dfqswide <- dfqs %>% pivot_wider( names_from = DisplayName, 
                                  values_from = Value, 
                                  id_cols = PatientDurableKey )
knitr::kable(dfqswide)
```



| PatientDurableKey|Have you experienced symptom A ? |Do you have family in UK ? |
|-----------------:|:--------------------------------|:--------------------------|
|                 1|no                               |yes                        |
|                 2|yes                              |no                         |

[add how to deal with multiple values per patient-question combination either if there is a record-id column or not]

In some cases there can be duplicate values per patient-question combination. This can be because a form was started and not completed for a patient. In that case the warning message from pivot_wider gives an indication of how to detect the duplicates.



## Patient Demographics

Patient demographics may be provided in a separate table extracted from Caboodle, also with a PatientDurableKey. The shared column can be used to join the two tables together to allow answers to be summarised by demographics.



```r

dfpatient <- read_csv("data//patient1.csv")

dfqswidejoin <- dfqswide %>% left_join(dfpatient, by="PatientDurableKey")

knitr::kable(dfqswidejoin)
```



| PatientDurableKey|Have you experienced symptom A ? |Do you have family in UK ? | AgeInYears|Gender |
|-----------------:|:--------------------------------|:--------------------------|----------:|:------|
|                 1|no                               |yes                        |         25|Female |
|                 2|yes                              |no                         |         56|Male   |
