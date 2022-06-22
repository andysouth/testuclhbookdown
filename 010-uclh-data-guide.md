# Data at UCLH

## Caboodle and Clarity

Data entered into EPIC are stored in data warehouses called Caboodle and Clarity.    

These data can be extracted using SQL by members of Information services teams.    

Extracting data in a format that makes it relatively easy to visualise and analyse may be a complicated process.

[Could we start from something like below to summarise the most commonly requested data and how to use them ?]
 
The data most frequently used are :
 
1. Patient Demographics 
2. Lab components
3. Flowsheets
4. Smartdata elements
5. Diagnoses
6. Medication
7. Encounters
 
[Can we say more about each of the above under headings like this ?]
 
* What are the most commonly requested fields ?
* Patient identifiers (DurableKey vs MRN) and other keys
* Data Codes and where can they be looked up
* Data Labels/Names
* Data Values (are there separate fields for numeric, text values etc.)
* Dates
* Any fields that identify whether values are current
 
How best to extract a particular measurement for a cohort ? How/where to look up codes (e.g. from Epic front end or elsewhere).

These data are stored in separate tables and may be provided as separate data files or joined as a part of the extraction process.


## OMOP

The Observational Medical Outcomes Partnership (OMOP) Common Data Model (CDM) is an open community data standard, designed to standardize the structure and content of observational data and to enable efficient analyses. UCLH is moving to using OMOP in 2022. OMOP allows data to be shared between institutions in a common format enabling collaborative analyses.

EPIC data are converted (mapped) to be held in OMOP data tables. 

This link documents how [critical care data can be stored in OMOP](https://uclh-criu.github.io/hic-alchemist-docs/).


## EMAP

The [Experimental Medical Applications Platform](https://www.uclhospitals.brc.nihr.ac.uk/criu/data-infrastructure), developed in UCLH is a non-operational “mirror” of a subset of UCLH data (historical and live) to support research.

[Links to emap documentation](https://github.com/inform-health-informatics/emap_documentation).


## Other

...



