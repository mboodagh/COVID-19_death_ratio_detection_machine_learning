# General description

To stave off the spread of the COVID-19, the authorities in the US employed different strategies, including the mask mandate order issued by the states' governors. In the current work, we defined a parameter called the average death ratio as the monthly average of the number of daily deaths to the monthly average number of daily cases to analyze the effectiveness of masks. We utilized survey data to quantify people's abidance by the mask mandate order. Additionally, we implicitly addressed the extent to which people abide by the mask mandate order that may depend on some parameters like population, income, and education level. Using different machine learning classification algorithms, we investigated how the decrease or increase in death ratio for the counties in the US West Coast correlates with the input parameters. The file **COVID_19_death_ratio.ipynb** contains all the necessary information on how to implement different machine learning algorithms for classification.The file **data** contains all the data for the counties of the three states of California, Oregon, and Washington.

![PDFtoJPG me-1 (1)](https://user-images.githubusercontent.com/60017299/143766094-dcbf4414-e6e6-4f4a-bf4e-f8c5e9671237.jpg)

# Motivation
The recent COVID-19 pandemic has affected millions of people worldwide and led to the tragic death of many innocent lives. The lack of a certain treatment at the beginning of the pandemic traumatized the populace. As a result, state officials began to impose legislative guidelines, including mandatory use of masks and closure of businesses such as bars and restaurants. Shutting down different businesses has been sporadic due to its adverse economic impact, but obligatory face coverings order is still in effect across the US. In this respect, the effectiveness of facial masks gains further importance and requires scientific studies.

Over the years, the effectiveness of face masks has been studied. However, the cardinal point that has not garnered enough attention is the relationship between the degree of exposure to the virus and its mortality rate. Some researchers presented the idea that the severity of the symptoms correlates with the extent of exposure to justify the high death rate in healthcare workers. Unfortunately, there is no universal trend that can predict the relationship between the dose of the virus and the severity of the resulting symptoms. A Machine Learning (ML) analysis can be instrumental in shedding light on the possible correlation between the public use of masks and changes in the mortality rate. The success of implementing ML and Artificial Intelligence (AI) techniques in the previous pandemics has convinced researchers to use them as precious tools in fighting against the current outbreak.

In the proposed work, utilizing different ML classification algorithms, we aim to unveil how the change in the mortality rate correlates with certain features. The features will be chosen in a way that they can reflect abidance by MM order in different counties.

# Methodology

We defined the parameter of interest as the ratio of the monthly average number of deaths to the monthly average number of cases, referred to as the death ratio, which can be interpreted as a measure of the severity of the disease.
The effective date of the executive orders by the governors, requiring mask mandate at all the counties in the three West Coast states of California, Oregon, and Washington, has been identified, which is publicly available. We used the average death ratio one month before and after the order to study the mortality rate.

It is a hard task to directly determine the exact percentage of the population that follows the MM order and uses face coverings. As a result, it is necessary to come up with features that can indirectly capture how likely is an individual to follow the recommended practice. For bridging this gap, four main features, including county population, median household income, education level and mask usage based on New York Times survey the are chosen as primary indicators. Furthermore, we used survey data provided by the New York Times that quantifies the mask usage from 7/2/2020 to 7/14/2020. Since the survey timeline lies within the month after the MM order for all three studied states, it is valid to use its data for our purpose.

Classic ML methods of Logistic Regression and Naive Bayes classifier are used. In addition, ensemble learning-based models, Random Forest and Extra Trees, are also analyzed. Moreover, the extreme boosting method, XGBoost is explored. Other methods such as Support Vector Machine, K-Nearest Neighbors, Decision Trees, and Neural Network are additionally used for prediction of effect of Mask Mandate on mortality rate.

# Results

The change in death ratio from one month before to one month after the date of mandating face-covering in the three states is visualized for each county as shown in the below figure.

![fig2](https://user-images.githubusercontent.com/60017299/143769413-d032e425-4192-418d-aaf4-8bf8c47ef4d7.png)

The effect of each feature on the change of death ratio is visualized by the correlation heatmap provided in the below figure. Each row of the complete correlation matrix is an appropriate indicator of how correlated that feature is with the change in death ratio. A more negative value implies that the increase of that specific feature is positively correlated by a decrease in the change of death ratio. For instance,  an increase in population, median income, and education level would result in a decrease in the change of death ratio.

![fig3](https://user-images.githubusercontent.com/60017299/143769811-c4595b0c-f091-43b1-a565-21aa3b70cc92.png)

Furthermore, to get some insight about the possible patterns in the death ratios variations, the average percentage of people who use masks with different frequencies across all the counties experiencing both increase and decrease in their death ratios is illustrated in the below figure. As expected, the average percentage of people who always wear a mask is slightly higher for the decreasing category, but in both categories, the values are the smallest for Oregon. Moreover, the average percentage of people who never use a mask is lower for the decreasing category in all 3 states, which is also intuitively sensible. Although there are no prominent and consistent patterns for the remaining mask usage frequencies, these observations could implicitly and partially describe why there is a small increase in the overall death ratio in Oregon. However, since the mask usage data is from an NYT survey over a limited period (12 days), the observations in  cannot explain the entire underlying phenomenon. According to a recent study, several factors are attributing to the possibility of a person following or not following the health guidelines set by the state officials. Therefore, three features among these parameters plus the aforementioned mask usage as the fourth feature have been used to conduct the current study.






