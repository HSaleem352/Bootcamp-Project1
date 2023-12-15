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
Dean:
#grouping age, Covid severity and cancer status for analysis 
age_covid_df = analysis_df[['der_age_trunc', 'severity_of_covid_19_v2', 'der_cancer_status_v4']]

# Filter out rows with unknown cancer status
age_covid_df = age_covid_df[age_covid_df['der_cancer_status_v4'] != 'Unknown']

# Filter out rows with unknown COVID severity
age_covid_df = age_covid_df[age_covid_df['severity_of_covid_19_v2'].notna()]

```
Mina:
The following code would change the style of the graph to be in a pastel color.
```python
plt.style.use('seaborn-v0_8-pastel')
```
In order for the saved graph to not be cut-off the following code is used.
```python
plt.savefig("Smoking_Output_Data/SmokingQ_Plot(6).png", bbox_inches="tight")
```
Shan:
The following code was used to generate a multiple line chart that illustrates the distribution of data among various racial groups (Race) concerning COVID-19 severity.
```python
#Plot the data points for each racial group with markers
plt.figure(figsize=(10, 6))
for index, row in df.iterrows():
    plt.plot(row.index[1:], row.values[1:], marker='o', label=row['Race'])
plt.title('COVID-19 Severity by Race')
```

Hamza:
The following code was used to create the bar graphs with the count of the entries. This is known as a count plot. This is available in the seaborn library. 
```python
barplot = sns.countplot(US_residence_df_clean, x = 'urban_rural', hue = 'severity_of_covid_19_v2')
```
API:
The following code was used to remove all the spans in order to extract only the text. 
```python
soup = BeautifulSoup("""<h4>What about cost?</h4>
<p><span><span><span><span><span><span><span>Under the&nbsp;Affordable Care Act, insurance plans must cover mammograms for women over age 40. Depending on your insurance plan, you may be able to get mammograms at no cost to you. Check with your insurance company to find out more. </span></span></span></span></span></span></span></p>
<p><span><span><span><span><span><span><span>Medicare also covers mammograms for women over age 40 at no cost. href="https://health.gov/myhealthfinder/api/outlink/myhealthfinder.json/http/www.medicare.gov/coverage/mammograms.html?_label_=Find+out+about+Medicare+coverage+for+mammograms">Find out about Medicare coverage for mammograms.</span></span></span></span></span></span></span></p>
<p><span><span><span><span><span><span><span>If you don’t have insurance, you can still get mammograms. href="https://health.gov/myhealthfinder/api/outlink/myhealthfinder.json/https/www.cdc.gov/cancer/nbccedp/screenings.htm?_label_=Find+a+program+near+you+that+offers+free+or+low-cost+mammograms">Find a program near you that offers free or low-cost mammograms.</span></span></span></span></span></span></span></p>
<p><span><span><span><span><span><span><span>To learn more, check out these resources:</span></span></span></span></span></span></span></p>
<ul>
	<p><span><span><span> href="https://health.gov/myhealthfinder/api/outlink/myhealthfinder.json/https/www.healthcare.gov/preventive-care-women/?_label_=Free+preventive+care%26nbsp%3Bfor+women+covered+by+the+Affordable+Care+Act">Free preventive care&nbsp;for women covered by the Affordable Care Act</span></span></span></p>
	<p><span><span><span> href="https://health.gov/myhealthfinder/api/outlink/myhealthfinder.json/https/www.healthcare.gov/health-care-law-protections/?_label_=How+the+Affordable+Care+Act+protects+you">How the Affordable Care Act protects you &nbsp;&nbsp;</span></span></span></p>
	<p> href="https://health.gov/myhealthfinder/api/outlink/myhealthfinder.json/https/marketplace.cms.gov/technical-assistance-resources/c2c-roadmap.pdf?_label_=Understanding+your+health+insurance+and+how+to+use+it+%5BPDF+-+698%26nbsp%3BKB%5D" id="anch_81">Understanding your health insurance and how to use it [PDF - 698&nbsp;KB]</p>
</ul>""", 'html.parser')

p_tags = soup.find_all('p')
for p in p_tags:
    print(p.get_text())
```





## Limitations
1. Vaccination status was not included in the study, as vaccines were not available during the predominant time frame for this cohort.
2. Confounding variables include drivers for inequity, such as socio-economic status, occupation, income, residence, education, and insurance status, limits insights into the root causes of disparities.
3. The study's focus on females and the United States may limit the generalizability of findings to other demographic groups or regions.
4. The dataset only focuses on 2 conditions, breast cancer and covid-19, so there could be other factors affecting covid-19 cases.
5. The data does not dive deeper into the history of smoking, rather generalizes if the subject smoked or not.

## Analysis 

**1. What is the isolated effect of age on the risk of COVID-19 and Breast Cancer severe outcomes? - Dean** 

In this study involving approximately 1400 women, the average age was found to be 58 years, regardless of their COVID-19 diagnosis or cancer status. In particular, when applying a one-sample t-test at the 95% confidence level, our analysis did not find sufficient evidence to reject the null hypothesis, which posits that the average age is 58 years. This holds across different sub-groups of women categorized by their cancer status. In other words, there is no statistically significant deviation from the hypothesized mean age of 58 years for these sub-populations at the 95% confidence level. Furthermore, the age distributions within the overall population and across different cancer statuses seem to follow a normal distribution with a high degree of certainty (at the 99% confidence level).

Additionally, our data reveal notable age differences among COVID-19 patients with varying degrees of severity. Patients hospitalized for COVID-19 (classified as having moderate status) and those admitted to the ICU (severe status) tend to be older on average, with mean ages of 64.28 and 59.03 years, respectively. This contrasts with the average age of 58 years observed in individuals diagnosed with active and progressing cancer.


**2. Is smoking a factor to have a severe COVID for individuals with Breast Cancer? - Mina**

  In order to answer this question, a step by step procedure was taken. First, the overall smoking status over the entire data set was analyzed. The data was isolated and cleaned for the smoking status only. This led to a bar graph to be created to display the differences between the individuals who ever have smoked in their life and the individuals who never have smoked in their life. The Smoking_Plot(1) displays that in our dataset, the number of people who has never smoked in their life is higher than the number of people who are either a current or former smokers. Next, the number of individuals who had breast cancer at the time of COVID-19 diagnosis and the smoking status was analyzed. The data was isolated and cleaned for this purpose. Then, a dataframe was created in order to create another bar graph called Smoking_Plot(2) to be able to compare the outcomes. Refering to this plot, the number of non-smoker individuals for all three breast cancer statuses (Active and responding, Active and stable, Active and progressing) was higher than the number of smokers, showing that the smoking status did not have an effect on the breast cancer statuses. Next, the severity of COVID-19 was compared to the smoking status. The data was isolated and cleaned for this purpose. Then a dataframe was created in order to create a bar graph called Smoking_Plot(3) to be able to compare the outcomes. Refering to this plot, the number of non-smoker individuals for all three COVID-19 severity types (Mild, Moderate, Severe) was higher than the number of smokers, showing that being a smoker does not have an effect on the severity of COVID-19. Lastly, the breast cancer statuses and the severity of COVID-19 were compared to the smoking status to check if being a smoker for the individuals with different type of breast cancer has an effect on the severity of the COVID-19. For this purpose, the data was isolated and cleaned. Then, three different dataframes were created for each severity of COVID-19. Each dataframe compares the severity of COVID-19 and the three statuses of breast cancer with the smoking status. Plots Smoking_Plot(4), Smoking_Plot(5), and Smoking_Plot(6) display the results. Refering to these plots, it can be concluded that being a smoker while having a breast cancer, does not have an effect on the COVID-19 severity.

  The hypothesis for this experiment was that "Individuals who smoke and have Breast Cancer have a higher chance of having a severe COVID compared to the individuals who do not smoke". However, looking at the bar graphs and with the analysis which was done, it could be seen that smoking does not have an effect on COVID-19 severity for individuals with breast cancer. A hypothesis testing called chi-squared was also done to test the hypothesis. Two different groups of smokers and non-smokers for severe type of COVID-19 for individuals with breast cancer were tested. This resulted in a p-value of 0.30 which is greater that 0.05. Therefore, the null hypothesis cannot be rejected and it can be concluded that there is no significant difference between the two data sets and as a result, individuals who smoke and have Breast Cancer do not have a higher chance of having a severe COVID compared to the individuals who do not smoke.  

  Please note that the dataset does not exactly dive deep into the history of smoking. It generalizes if the subject smoked or not. Also, in the dataset the overall number of people who smoke is lower than the number of people who do not. This might have been affected the outcome of this analysis. 
  
**3. Amongst all the races with different BC statuses, is smoking a factor for them to have COVID? - Mina**

  In order to answer this question, the data was isolated and cleaned. Then through a step by step process, three different dataframes were created for each breast cancer statuses. Each dataframe compares the race/ethnicity for all types of COVID-19 severity with the smoking status. Pie charts Smoking_Plot(7), Smoking_Plot(8), Smoking_Plot(9), Smoking_Plot(10), Smoking_Plot(11), and Smoking_Plot(12) display the results for smokers and non-smokers. Refering to these plots, it can be concluded that amongst all the races smoking is not a factor for the individuals with active and stable as well as active and progressing breast cancer statuses to have COVID-19. However, amongst all the races smoking is a factor for the individuals with active and responding breast cancer status to have COVID-19.

  The hypothesis for this experiment was that "Amongst all the races with different breast cancer statuses, smoking is a factor for them to have COVID". However, looking at the pie charts and with the analysis which was done, it could be seen that amongst all the races smoking is not a factor for the individuals with active and stable as well as active and progressing breast cancer statuses to have COVID-19. However, amongst all the races smoking is a factor for the individuals with active and responding breast cancer status to have COVID-19. A hypothesis testing called chi-squared was also done to test the hypothesis. Two different groups of smokers and non-smokers were tested. This resulted in a p-value of 0.34 and 0.55 respectively for individuals with different races and active and stable as well as active and progressing breast cancer statuses which is greater than 0.05. Therefore, the null hypothesis cannot be rejected and it can be concluded that there is no significant difference between the two data sets and as a result, amongst all the races smoking is not a factor for the individuals with active and stable as well as active and progressing breast cancer statuses to have COVID-19. However, the p-value for the individuals with active and responding breast cancer status is 0.03 which is less than 0.05. Therefore, the null hypothesis is rejected and it can be concluded that there is a significant difference between the two data sets and as a result, amongst all the races smoking is a factor for the individuals with active and responding breast cancer status to have COVID-19.

  Please note that the dataset does not exactly dive deep into the history of smoking. It generalizes if the subject smoked or not. Also, in the dataset the overall number of people who smoke is lower than the number of people who do not. This might have been affected the outcome of this analysis.

**4. Does obesity and age have an affect on Covid with Breast Cancer? - Fozia**

 Age and COVID-19 Severity For People With Brest Cancer:
Our analysis revealed a noteworthy correlation between age and COVID-19 severity in breast cancer patients. Notably, individuals aged 49 to 68 tended to experience milder COVID-19 symptoms, while those in the age range of 58 to 79 exhibited more moderate symptoms. Severe cases were more prevalent in individuals aged 57 to 79. This insight emphasizes the importance of considering age as a factor in predicting COVID-19 outcomes among breast cancer patients.
In our analysis, we observed a discernible connection between a patient's age and the severity of their COVID-19 symptoms. This correlation suggests that as age increases, the likelihood of experiencing more severe symptoms also tends to rise. Specifically, breast cancer patients in the age range of 57 to 79 exhibited a higher prevalence of severe COVID-19 symptoms. This finding aligns with existing medical knowledge, as age is often recognized as a significant factor influencing the severity of respiratory illnesses, including COVID-19.
Understanding the Impact of Obesity on COVID-19 Severity in Breast Cancer Patients:
The analysis revealed a significant proportion of breast cancer patients tend to exhibit mild symptoms when infected with COVID-19. This insight may indicate that factors beyond obesity play a crucial role in determining the severity of symptoms.
Additionally
I checked into the correlation between age and obesity, which was found to be approximately -0.03. This negative correlation indicates a slight tendency for age and obesity to move in opposite directions among individuals with breast cancer. In simpler terms, as age increases, there is a subtle trend for obesity prevalence to decrease, and vice versa. It's essential to note that this correlation is relatively close to zero, signifying a weak association.
So, if someone is older, it doesn't necessarily mean they'll be obese. There are likely other things at play that have a more significant impact on whether someone with breast cancer is obese. It's like saying age is just one piece of the puzzle, and there's a lot more to consider. In summary, the connection we observed between age and obesity is there, but it's not a big deal. It tells us that age alone isn't the main factor determining whether someone with breast cancer is obese or not. We need to look at other factors to get the full picture and find the best ways to help these individuals.
In conclusion,
In summary, our findings highlight the complex interplay between age, obesity, and COVID-19 severity in breast cancer patients. Age emerged as a significant factor in predicting symptom severity, while obesity alone did not solely determine outcomes. The nuanced correlation between age and obesity reinforces the need to consider multiple factors for a comprehensive understanding of how these variables influence COVID-19 outcomes in individuals with breast cancer.

**5. How does race/ethnicity affect Covid with Breast Cancer? - Shan**

In order to answer this question, I conducted a comprehensive analysis of the relationship between race and two critical health factors: COVID-19 severity and breast cancer incidence. My hypothesis posits a positive correlation between race and the prevalence and severity of both conditions. The dataset I utilized encompasses data on race, COVID-19 severity, and cancer status, enabling a thorough examination of these associations.

In my analysis, I took measures to rectify sample population imbalances by employing a weighted averaging technique for each race category, including COVID-19 severity levels. This approach ensured equitable representation within the dataset.The findings of my study reveal compelling evidence of a significant association between Race/Ethnic Distribution and both COVID-19 severity and breast cancer status.Regarding COVID-19 severity, the Chi-Square test resulted in a p-value of 0.0044, which is below the conventional threshold of 0.05 for statistical significance. This outcome indicates a clear association between Race/Ethnic Distribution and the severity of COVID-19 cases. My analysis unveiled distinct patterns in COVID-19 severity among various racial and ethnic groups. In general, mild cases were the most prevalent, followed by moderate and severe cases. Notably, the 'Non-Hispanic Black,' 'Non-Hispanic AAPI,' and 'Other' categories exhibited higher percentages of moderate and severe COVID-19 cases. In contrast, the 'Hispanic' population experienced milder symptoms, while the 'Non-Hispanic White' group displayed a more balanced distribution. Factors contributing to these disparities may include variations in treatment, therapy (such as ICU admission and hospitalization), or pre-existing underlying health conditions among these racial groups.

Regarding breast cancer, the Chi-Square test yielded a Chi-squared value of 98.05 and an exceptionally low p-value of 2.81e-12, significantly below the conventional 0.05 threshold for statistical significance. This result underscores a robust and statistically significant association between Race/Ethnic Distribution and breast cancer status.Specifically, within the 'Remission or no evidence of disease, <5 years' category, several racial groups exhibit a higher prevalence, pointing to favorable early-stage cancer outcomes and successful treatments. Both the Hispanic and Non-Hispanic White populations display significant percentages in this category, suggesting a substantial number of individuals recovering from cancer within the first five years. However, when focusing on the 'Active' categories, it becomes evident that Hispanic and Non-Hispanic Asian American and Pacific Islander (AAPI) populations have a higher rate of active breast cancer cases. These 'Active' statuses encompass 'Active and progressing,' 'Active and responding,' and 'Active and stable.' This disparity in active breast cancer rates may be influenced by various factors, including genetic predispositions, socioeconomic status, access to healthcare, underlying health conditions, or other social determinants of health correlated with race and ethnicity.

In conclusion, my research emphasizes the critical role of Race/Ethnic Distribution in influencing the incidence and progression of both COVID-19 severity and breast cancer. These findings underscore the complexity of health disparities among different racial and ethnic groups and underscore the need for targeted healthcare interventions and strategies to comprehensively address these disparities, ultimately leading to improved health outcomes.

**6. Is the severity of covid-19 affected if the individuals live in urban, suburban, or rural areas? - Hamza**

  In this part of the analysis, the residence of the patients' has been studied. By residence, the analysis means if the patient lived in an urban, suburban, or rural setting. The first part of this analysis explores how many cases of Covid-19 were reported in each residence type. By just examining the pie chart, the suburban type had the most amount of cases reported followed by urban and then rural. This suggests that living in the suburbs or the city would have a higher chance of getting Covid-19. However, it should also be noted that there is a higher population living in suburbs and city compared to rural areas that the dataset does not consider. 
  Moreover, the analysis examines the severity of Covid-19 in each respective residence type. For this case, the severity is divided into 3 categories, mild, morderate, and severe. The null hypothesis is that the severity of Covid-19 is not affected by the type of residence. On the other hand, the alternate hypothesis is that the type of residence has an affect on the severity of Covid-19. In order to answer this hypothesis, the bar graphs were examined. The bar graphs show the number of cases reported as mild, morderate, or severe in each of the residence types. By visually inspecting the graphs, it would appear that there is a trend in the number of cases reported. The mild cases are very high, the morderate cases are about a quarter of the mild cases, and the severe cases are about one fifth of the morderate cases. This trend is similar in all three cases which suggests that there is no relevant association between the severity of Covid-19 and the type of residence. To futher examine this, the chi-square contingency test was performed yielding a p-value of 0.07. If the common threshold of 0.05 is used then the null hypothesis is acceptable. This means that there is no association between the type of residence and the severity of Covid-19. 
  Even though the null hypothesis is accepted, it should be noted that the p-value was very close to the threshold. This suggests that there might be some sort of association between the two factors. The analysis is limited by a number of factors such as the amount of data working with. The number of cases for rural areas are significantly lower than in other residence types, therefore, with more data, the result might lean on the alternate hypothesis.

  
**7. How does the timing of their breast cancer treatment affect their Covid outcomes? - Alex**

Cancer treatments can affect the immune system and its ability to respond to infection. According to the American Cancer Society, cancer treatments like chemotherapy and radiation therapy can cause a decrease in the number of white blood cells and thus decrease the body's capacity to respond to infection. Additionally, targeted therapy and immunotherapy are used to improve the immune system's ability to attack cancer cells, but can compromise their ability to fight off infections. In this analysis, I am looking at how the timing of the cancer treatment or the type of cancer treatment affects the severity of Covid by potentially compromising the immune system and its ability to respond to infection. I am hypothesizing that the closer the cancer treatment was given to COVID-19 infection, the more likely the patients are to have moderate or severe COVID-19 outcomes. I am also hypothesizing that there are more moderate or severe COVID-19 outcomes for individuals that were given BC therapy than compared to those that did not receive treatment during their COVID-19 infection. 

In order to perform this analysis, I first collected the proportion of individuals that had mild, moderate, or severe covid outcomes for each cancer timing. I plotted the individual counts on a bar chart to better visualize the data and then performed a chi squared analysis on the proportions. Since the p-value is greater than 0.05 for each covid-19 outcome data set, we fail to reject the null hypothesis and cannot say that there is a link between the timing of the cancer treatment and the covid-19 outcome. Further analysis and studies would have to be done to see how the timing of breast cancer treatment with COVID-19 affects COVID-19 recovery. 

Next, I examined individuals that underwent cytotoxic chemotherapy, targeted radiation, endocrine therapy, or immunotherapy as well as the proportion of individuals that underwent no breast cancer therapy and calculated the proportion of individuals that had mild, moderate, or severe outcomes for each type of BC therapy. I ploted the individual counts onto a bar chart to better visualize the data and performed a chi squared analysis on the proportions. Since the p-value is greater than 0.05 for each covid outcome group, we fail to reject the null hypothesis and cannot say that there is a link between the type of breast cancer therapy and the covid-19 outcome for these patients. We would have to conduct a further analysis on the correlation between the type of breast cancer therapy and the covid-19 outcome to see if and what kind of effect there is.

**8. API**

  The objective of this API was to retrieve information about breast cancer and the next steps. The API was filtered for females only, with age group around 60 Years Old since the dataset for this project reflects these filters. The API was retrieved from health.gov/myhealthfinder and only focuses on United States since the dataset only covers United States. This API states that breast cancer is one of the most common kinds of cancer in women. About 1 in 8 women in the United States will get breast cancer during her lifetime. Furthermore, breast cancer is a cancer that forms in breast tissue and like all cancers, it can spread to other parts of the body. The API further explains to talk with your doctor or nurse if the female notices any of these changes: A lump or an area that feels very firm in the breast or armpit, A change in the size, shape, or feel of the breast, Fluid (called discharge) coming out of a nipple, Skin on the breast that is itchy, red, flaky, or dimpled. Moreover, mammograms let the doctor or nurse look for lumps or other changes inside the breasts that can’t be felt from the outside. If the doctor finds a lump or another change in the breast tissue, other tests may be needed to find out if it’s cancer or not. The doctor or nurse may take a small bit of tissue from the breast for testing. This procedure is called a biopsy. Lastly, under the Affordable Care Act, insurance plans must cover mammograms for women over age 40. Depending on the insurance plan, mammograms might be free of cost. Check with the insurance company to find out more. However, this only relates to individuals in the United States.



## References 

**Mina**:
How to save a matplotlib figure and fix text cutting off: https://www.youtube.com/watch?v=C8MT-A7Mvk4
chi-squared test: Chat GPT

*** Hamza ***:
Used chatGPT for the sns.countplot() function. Sns is seaborn imported as sns and the countplot plots the length of rows for the categories. Then plots them as a bar graph
Used ChatGPT for chi2_contingency(). The chi-square contingency test is used to determine whether there is a significant association between two categorical variables.

**Alex**: 
- I used this link for background information on the link between cancer therapy and immune system: https://www.cancer.org/cancer/managing-cancer/side-effects/low-blood-counts/infections/why-people-with-cancer-are-at-risk.html
- I used this link for plotting multiple bar charts: https://www.geeksforgeeks.org/plotting-multiple-bar-charts-using-matplotlib-in-python/
- I used this to get the column names: https://www.geeksforgeeks.org/how-to-get-column-names-in-pandas-dataframe/
![image](https://github.com/HSaleem352/Bootcamp-Project1/assets/147428025/b6a83cde-2a3a-4271-9d28-df93000c4424)


**API**:
How To Eliminate Span & Other HTML Tags With BeautifulSoup: https://scrapeops.io/python-web-scraping-playbook/python-beautifulsoup-eliminate-span-html-tags/









