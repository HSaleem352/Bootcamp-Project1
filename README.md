# Cancer Research Group

## Description of Project

Our project is based on a study conducted in collaboration with the COVID-19 and Cancer Consortium (CCC19) registry. This investigation explores the intersection of COVID-19 and breast cancer (BC) in females, spanning the period from March 2020 to June 2021. The data encompasses a cohort of 1383 female participants diagnosed with breast cancer and confirmed SARS-CoV-2 infection. The median age of participants is 61 years, and the follow-up period extends to 90 days. To ensure diversity and representation, the cohort includes individuals from various geographic regions within the United States.

Our primary objective is to comprehensively assess the severity of COVID-19 outcomes among females with a history of breast cancer. Leveraging the CCC19 registry, we aim to identify specific factors influencing COVID-19 severity in this particular population. This knowledge is crucial for tailoring medical responses and interventions for individuals with breast cancer who contract COVID-19.

## The questions we're going to answer are:
1. What is the isolated effect of age on the risk of COVID-19 and Breast Cancer severe outcomes? - Dean 
2. Is smoking a factor to have a severe COVID for individuals with Breast Cancer? - Mina
3. Amongst all the races with different BC statuses, is smoking a factor for them to have COVID? - Mina
4. Does obesity and age have an affect on Covid with Breast Cancer? - Fozia
5. How does race/ethnicity affect Covid with Breast Cancer? - Shan
6. Is the severity of covid-19 affected if the individuals live in urban, suburban, or rural areas? - Hamza
7. How does the timing of their breast cancer treatment affect their Covid outcomes? - Alex

## API
- API used: https://health.gov/myhealthfinder
- The Website is found by Shan.
- The API Analysis is done by both Mina and Hamza.
- The API is used to gather general information about Breast Cancer. 

## Members of the group
-Hamza Saleem - @HSaleem352
-Mina Bagheri - @minalbm
-Dean Ninalga - @Ninalgad 
-Fozia - @FoziaY
-Shan Lian - @Lians03
-Alejandra - @AlejandraFeatherston

## Work Breakdown 
1. All group members will research databases on the topic and extract data from the ncbi.
2. All group members will be responsible for cleaning and merging the raw data.
3. Hamza and Mina well be responsible for APIs.
4. Dean will be analyzing the clean data and answering question #1
5. Mina will be analyzing the clean data and answering question #2,3
6. Fozia will be analyzing the clean data and answering question #4
7. Shan will be analyzing the clean data and answering question #5
8. Hamza will be analyzing the clean data and answering question #6
9. Alex will be analyzing the clean data and answering question #7
  
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

Hamza:
The following code was used to create the bar graphs with the count of the entries. This is known as a count plot. This is available in the seaborn library. 
barplot = sns.countplot(US_residence_df_clean, x = 'urban_rural', hue = 'severity_of_covid_19_v2')






## Limitations
1. Vaccination status was not included in the study, as vaccines were not available during the predominant time frame for this cohort.
2. Confounding variables include drivers for inequity, such as socio-economic status, occupation, income, residence, education, and insurance status, limits insights into the root causes of disparities.
3. The study's focus on females and the United States may limit the generalizability of findings to other demographic groups or regions.
4. The dataset only focuses on 2 conditions, breast cancer and covid-19, so there could be other factors affecting covid-19 cases.
5. The data does not dive deeper into the history of smoking, rather generalizes if the subject smoked or not.

## Analysis 

**1. What is the isolated effect of age on the risk of COVID-19 and Breast Cancer severe outcomes? - Dean** 

On average, women were 58 years of age independent of COVID-19 diagnosis and cancer stats. These results, based on a sample of about 1400 women, are considered accurate 19 times out of 20. In other words,  we cannot provide sufficient evidence to reject the null hypothesis at the hypothesized average age of 58 at the 95% confidence level using the one-sample t-test. Moreover, the age distribution of women across each cancer status also appears to be 58. Where the one-sample t-test, cannot provide sufficient evidence to suggest otherwise, at the 95% confidence level. Indeed, the population age distributions and age distributions across each cancer status appear normally distributed at the 99% confidence level.

The patients with moderate status (patients hospitalized for COVID), and severe status (patients admitted to the ICU) tend to be much older. We find that on average, patients with moderate and severe COVID are 64, and 59 years old, respectively. These averages are much higher than the average age of 58 for people with active cancer statuses.


**2. Is smoking a factor to have a severe COVID for individuals with Breast Cancer? - Mina**

  In order to answer this question, a step by step procedure was taken. First, the overall smoking status over the entire data set was analyzed. The data was isolated and cleaned for the smoking status only. This led to a bar graph to be created to display the differences between the individuals who ever have smoked in their life and the individuals who never have smoked in their life. The Smoking_Plot(1) displays that in our dataset, the number of people who has never smoked in their life is higher than the number of people who are either a current or former smokers. Next, the number of individuals who had breast cancer at the time of COVID-19 diagnosis VS. the smoking status was analyzed. The data was isolated and cleaned for this purpose. Then, a dataframe was created in order to create another bar graph called Smoking_Plot(2) to be able to compare the outcomes. Refering to this plot, the number of non-smoker individuals for all three breast cancer statuses (Active and responding, Active and stable, Active and progressing) was higher than number of smokers, showing that the smoking status did not have an effect on the breast cancer statuses. Next, the severity of COVID-19 was compared to the smoking status. The data was isolated and cleaned for this purpose. Then a dataframe was created in order to create a bar graph called Smoking_Plot(3) to be able to compare the outcomes. Refering to this plot, the number of non-smoker individuals for all three COVID-19 severity types (Mild, Moderate, Severe) was higher than number of smokers, showing that being a smoker does not have an effect on the severity of COVID-19. Lastly, the breast cancer statuses and the severity of COVID-19 was compared to the smoking status to check if the being a smoker for the individuals with different type of breast cancer has an effect on the severity of the COVID-19. For this purpose, the data was isolated and cleaned. Then, three different dataframes were created for each severity of COVID-19. Each dataframe compares the severity of COVID-19 and the three statuses of breast cancer with the smoking status. Plots Smoking_Plot(4), Smoking_Plot(5), and Smoking_Plot(6) display the results. Refering to these plots, it can be concluded that being a smoker while having a breast cancer, does not have an effect on the COVID-19 severity.

  The hypothesis for this experiment was that "Individuals who smoke and have Breast Cancer have a higher chance of having a severe COVID compared to the individuals who do not smoke". However, looking at the bar graphs and with the analysis which was done, it could be seen that smoking does not have an effect on COVID-19 severity for individuals with breast cancer. A hypothesis testing called chi-squared was also done to test the hypothesis. Two different groups of smokers and non-smokers for severe type of COVID-19 for individuals with breast cancer were tested. This resulted in a p-value of 0.30 which is greater that 0.05. Therefore, the null hypothesis cannot be rejected and it can be concluded that there is no significant difference between the two data sets and as a result, individuals who smoke and have Breast Cancer do not have a higher chance of having a severe COVID compared to the individuals who do not smoke.  
  
**4. Amongst all the races with different BC statuses, is smoking a factor for them to have COVID? - Mina**

  In order to answer this question, the data was isolated and cleaned. Then through a step by step process, three different dataframes were created for each breast cancer statuses. Each dataframe compares the race/ethnicity for all types of COVID-19 severity with the smoking status. Pie charts Smoking_Plot(7), Smoking_Plot(8), Smoking_Plot(9), Smoking_Plot(10), Smoking_Plot(11), and Smoking_Plot(12) display the results for smokers and non-smokers. Refering to these plots, it can be concluded that amongst all the races smoking is not a factor for the individuals with active and stable as well as active and progressing breast cancer statuses to have COVID-19. However, amongst all the races smoking is a factor for the individuals with active and responding breast cancer status to have COVID-19.

  The hypothesis for this experiment was that "Amongst all the races with different breast cancer statuses, smoking is a factor for them to have COVID". However, looking at the pie charts and with the analysis which was done, it could be seen that amongst all the races smoking is not a factor for the individuals with active and stable as well as active and progressing breast cancer statuses to have COVID-19. However, amongst all the races smoking is a factor for the individuals with active and responding breast cancer status to have COVID-19. A hypothesis testing called chi-squared was also done to test the hypothesis. Two different groups of smokers and non-smokers were tested. This resulted in a p-value of 0.34 and 0.55 respectively for individuals with different races and active and stable as well as active and progressing breast cancer statuses which is greater than 0.05. Therefore, the null hypothesis cannot be rejected and it can be concluded that there is no significant difference between the two data sets and as a result, amongst all the races smoking is not a factor for the individuals with active and stable as well as active and progressing breast cancer statuses to have COVID-19. However, the p-value for the individuals with active and responding breast cancer status is 0.03 which is less than 0.05. Therefore, the null hypothesis is rejected and it can be concluded that there is a significant difference between the two data sets and as a result, amongst all the races smoking is a factor for the individuals with active and responding breast cancer status to have COVID-19.

**5. Does obesity and age have an affect on Covid with Breast Cancer? - Fozia**

**6. How does race/ethnicity affect Covid with Breast Cancer? - Shan**

**7. Is the severity of covid-19 affected if the individuals live in urban, suburban, or rural areas? - Hamza**

  In this part of the analysis, the residence of the patients' has been studied. By residence, the analysis means if the patient lived in an urban, suburban, or rural setting. The first part of this analysis explores how many cases of Covid-19 were reported in each residence type. By just examining the pie chart, the suburban type had the most amount of cases reported followed by urban and then rural. This suggests that living in the suburbs or the city would have a higher chance of getting Covid-19. However, it should also be noted that there is a higher population living in suburbs and city compared to rural areas that the dataset does not consider. 
  Moreover, the analysis examines the severity of Covid-19 in each respective residence type. For this case, the severity is divided into 3 categories, mild, morderate, and severe. The null hypothesis is that the severity of Covid-19 is not affected by the type of residence. On the other hand, the alternate hypothesis is that the type of residence has an affect on the severity of Covid-19. In order to answer this hypothesis, the bar graphs were examined. The bar graphs show the number of cases reported as mild, morderate, or severe in each of the residence types. By visually inspecting the graphs, it would appear that there is a trend in the number of cases reported. The mild cases are very high, the morderate cases are about a quarter of the mild cases, and the severe cases are about one fifth of the morderate cases. This trend is similar in all three cases which suggests that there is no relevant association between the severity of Covid-19 and the type of residence. To futher examine this, the chi-square contingency test was performed yielding a p-value of 0.07. If the common threshold of 0.05 is used then the null hypothesis is acceptable. This means that there is no association between the type of residence and the severity of Covid-19. 
  Even though the null hypothesis is accepted, it should be noted that the p-value was very close to the threshold. This suggests that there might be some sort of association between the two factors. The analysis is limited by a number of factors such as the amount of data working with. The number of cases for rural areas are significantly lower than in other residence types, therefore, with more data, the result might lean on the alternate hypothesis.

  
**8. How does the timing of their breast cancer treatment affect their Covid outcomes? - Alex**



## References 











