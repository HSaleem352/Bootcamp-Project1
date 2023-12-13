# Cancer Research Group

## Description of Project

Our project is based on a study conducted in collaboration with the COVID-19 and Cancer Consortium (CCC19) registry. This investigation explores the intersection of COVID-19 and breast cancer (BC) in females, spanning the period from March 2020 to June 2021. The data encompasses a cohort of 1383 female participants diagnosed with breast cancer and confirmed SARS-CoV-2 infection. The median age of participants is 61 years, and the follow-up period extends to 90 days. To ensure diversity and representation, the cohort includes individuals from various geographic regions within the United States.

Our primary objective is to comprehensively assess the severity of COVID-19 outcomes among females with a history of breast cancer. Leveraging the CCC19 registry, we aim to identify specific factors influencing COVID-19 severity in this particular population. This knowledge is crucial for tailoring medical responses and interventions for individuals with breast cancer who contract COVID-19.

## The questions we're going to answer are:
1. What is the isolated effect of age on the risk of COVID-19 and Breast Cancer severe outcomes? - Dean 
2. Does smoking have an effect on COVID severity on individuals with Breast Cancer? - Mina
3. Amongst all the races with different BC statuses, is smoking a factor for them to have COVID? - Mina
4. Does obesity and age have an affect on Covid with Breast Cancer? - Fozia
5. How does race/ethnicity affect Covid with Breast Cancer? - Shan
6. Area of Patients' residence vs Covid with Breast Cancer. - Hamza
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

## Limitations
1. Vaccination status was not included in the study, as vaccines were not available during the predominant time frame for this cohort.
2. Confounding variables include drivers for inequity, such as socio-economic status, occupation, income, residence, education, and insurance status, limits insights into the root causes of disparities.
3. The study's focus on females and the United States may limit the generalizability of findings to other demographic groups or regions.
4. The dataset only focuses on 2 conditions, breast cancer and covid-19, so there could be other factors affecting covid-19 cases.
5. The data does not dive deeper into the history of smoking, rather generalizes if the subject smoked or not.

## References 

## Analysis 

**1. What is the isolated effect of age on the risk of COVID-19 and Breast Cancer severe outcomes? - Dean** 
**2. Does smoking have an effect on COVID severity on individuals with Breast Cancer? - Mina**

    In order to answer this question, a step by step procedure was taken. First, the overall smoking status over the entire data set was analyzed. The data was isolated and cleaned for the smoking status only. This has leaded to a bar graph to be created to display the differences between the individuals who has ever smoked in their life and the individuals who has never smoked in their life. The Smoking_Plot(1) displays that in our dataset, the number of people who has never smoked in their life is higher than the number of people who are either a current or former smokers. Next, the number of individuals who had breast cancer at the time of COVID-19 diagnosis VS. the smoking status was analyzed. The data was isolated and cleaned for this purpose. Then, a dataframe was created in order to creat another bar graph called Smoking_Plot(2) to be able to compare the outcomes. Refering to this plot, the number of non-smoker individuals for all three breast cancer statuses (Active and responding, Active and stable, Active and progressing) was lower than number of smokers, showing that the smoking status did not have an effect on the breast cancer statuses. Next, the severity of COVID-19 was compared to the smoking status. The data was isolated and cleaned for this purpose.	
   
**4. Amongst all the races with different BC statuses, is smoking a factor for them to have COVID? - Mina
5. Does obesity and age have an affect on Covid with Breast Cancer? - Fozia
6. How does race/ethnicity affect Covid with Breast Cancer? - Shan
7. Area of Patients' residence vs Covid with Breast Cancer. - Hamza
8. How does the timing of their breast cancer treatment affect their Covid outcomes? - Alex**














