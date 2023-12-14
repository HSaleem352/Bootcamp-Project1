# Cancer Research Group

## Description of Project

Our project is based on a study conducted in collaboration with the COVID-19 and Cancer Consortium (CCC19) registry. This investigation explores the intersection of COVID-19 and breast cancer (BC) in females, spanning the period from March 2020 to June 2021. The data encompasses a cohort of 1383 female participants diagnosed with breast cancer and confirmed SARS-CoV-2 infection. The median age of participants is 61 years, and the follow-up period extends to 90 days. To ensure diversity and representation, the cohort includes individuals from various geographic regions within the United States.

Our primary objective is to comprehensively assess the severity of COVID-19 outcomes among females with a history of breast cancer. Leveraging the CCC19 registry, we aim to identify specific factors influencing COVID-19 severity in this particular population. This knowledge is crucial for tailoring medical responses and interventions for individuals with breast cancer who contract COVID-19.

## The questions we're going to answer are:
1. determining and examining outliers - Dean 
2. Does smoking have an affect on Covid with Breast Cancer on male and female - Mina
3. Does obesity and age have an affect on Covid with Breast Cancer on male and female - Fozia
4. How does race/ethnicity affect Covid with Breast Cancer on male and female - Shan
5. Area of Patients' residence vs Covid with Breast Cancer on male and female - Hamza
6. Alex Q here
7. 
8. 

## Members of the group
-Hamza Saleem - @HSaleem352
-Mina Bagheri - @minalbm
-Dean Ninalga - @Ninalgad 
-Fozia - @FoziaY
-Shan Lian - @Lians03
-Alejandra - @AlejandraFeatherston


## Work Breakdown 
1. All group members will research databases on the topic and extract data from the ncbi.
2.All group members will be responsible for cleaning and merging the raw data.
3. Hamza and Mina well be responsible for APIs.
4. Alex will be analyzing the clean data and answering question
5. Fozia will be analyzing the clean data and answering question 
6. Mina will be analyzing the clean data and answering question 
7. Shan will be analyzing the clean data and answering question 
8. Hamza will be analyzing the clean data and answering question 
9. Dean will be analyzing the clean data and answering question 


## Datasets used 
Nagaraj, G., Khaki, A., & Shah, D. (2023). Covid-19 and Cancer Consortium (CCC19) breast cancer and racial disparities outcomes study. Zenodo. https://doi.org/10.5281/zenodo.7644334


## Code snippets
```python
#grouping age, Covid severity and cancer status for analysis 
age_covid_df = analysis_df[['der_age_trunc', 'severity_of_covid_19_v2', 'der_cancer_status_v4']]

# Filter out rows with unknown cancer status
age_covid_df = age_covid_df[age_covid_df['der_cancer_status_v4'] != 'Unknown']

# Filter out rows with unknown COVID severity
age_covid_df = age_covid_df[age_covid_df['severity_of_covid_19_v2'].notna()]

``` 
# Breast Cancer and COVID-19 Analysis

## Overview

This repository contains Python code for analyzing the correlation and impact of age, obesity, and breast cancer status on the severity of COVID-19 outcomes in individuals with breast cancer.

## Analysis Steps

- **Data Collection:** Loaded the dataset into a pandas DataFrame using `pd_read`.

- **Data Cleaning:** Ensured proper data types and created a structured analysis DataFrame.

- **Exploratory Data Analysis:**

  - Visualized the distribution of COVID-19 severity levels in individuals with breast cancer.
  
  - Explored the distribution of cancer status to gain insights into the dataset characteristics.

  - Investigated the correlation between age and obesity status to understand potential relationships.

## Why it was Done

The analysis aims to explore correlations and patterns between age, obesity, and COVID-19 severity in individuals with breast cancer, providing insights into factors influencing COVID-19 outcomes in this specific population.

## How it was Done

The analysis was conducted using Python, leveraging pandas, seaborn, and matplotlib for data manipulation and visualization. The code is organized into distinct steps for clarity.


## Resources Used
I have referred to a few online resources for certain tasks with difficulty, namely: Stackoverflow and Chatgpt
## Limitations
1. Vaccination status was not included in the study, as vaccines were not available during the predominant time frame for this cohort.
2. Lack of additional information on drivers for inequity, such as socio-economic status, occupation, income, residence, education, and insurance status, limits insights into the root causes of disparities.
3. The study's focus on females and the United States may limit the generalizability of findings to other demographic groups or regions.

