**In this project, recommendations and insights are generated by firstly using exploratory data analysis on the "Turkiye Student Evaluation(TSE)" dataset [can be found here](https://archive.ics.uci.edu/dataset/262/turkiye+student+evaluation) and "Bank Marketing Campaign(BMC)" dataset [can be found here](https://archive.ics.uci.edu/dataset/222/bank+marketing).**

**I then apply descriptive analytics to TSE, predictive analytics to BMC and lastly prescriptive analytics on the results generated from both datasets to provide some insight and recommendations of actions a school (TSE dataset) and a bank (BMC dataset) can take up for improvement.**

## Table of Contents
[**About the project**](https://github.com/Kishawn-Dorman/ANOVA-Tests-and-Regression-Modelling#about-the-project) 

[**Section 1 - Company A (Descriptive Statistics)**](https://github.com/Kishawn-Dorman/ANOVA-Tests-and-Regression-Modelling#section-1---company-a-descriptive-statistics) 
- [**Objective**](https://github.com/Kishawn-Dorman/ANOVA-Tests-and-Regression-Modelling#objective)
- [**Process**](https://github.com/Kishawn-Dorman/ANOVA-Tests-and-Regression-Modelling#process)
- [**Results**](https://github.com/Kishawn-Dorman/ANOVA-Tests-and-Regression-Modelling#results)

[**Section 1 - Results Assessment and Conclusions**](https://github.com/Kishawn-Dorman/ANOVA-Tests-and-Regression-Modelling#section-1---results-assessment-and-conclusions) 
- [**Executive Summary**](https://github.com/Kishawn-Dorman/ANOVA-Tests-and-Regression-Modelling#executive-summary)
- [**Aim and Objectives**](https://github.com/Kishawn-Dorman/ANOVA-Tests-and-Regression-Modelling#aim-and-objectives)
- [**Analysis**](https://github.com/Kishawn-Dorman/ANOVA-Tests-and-Regression-Modelling#analysis)
- [**Recommendations**](https://github.com/Kishawn-Dorman/ANOVA-Tests-and-Regression-Modelling#recommendations)
- [**Limitations**](https://github.com/Kishawn-Dorman/ANOVA-Tests-and-Regression-Modelling#limitations)

[**Section 2 - Company B (Predictive Statistics)**](https://github.com/Kishawn-Dorman/ANOVA-Tests-and-Regression-Modelling#section-2---company-b-predictive-statistics) 
- [**Objective**](https://github.com/Kishawn-Dorman/ANOVA-Tests-and-Regression-Modelling#objective-1)
- [**Process**](https://github.com/Kishawn-Dorman/ANOVA-Tests-and-Regression-Modelling#process-1)
- [**Results**](https://github.com/Kishawn-Dorman/ANOVA-Tests-and-Regression-Modelling#results-1)

[**Section 2 - Results Assessment and Conclusions**](https://github.com/Kishawn-Dorman/ANOVA-Tests-and-Regression-Modelling#section-2---results-assessment-and-conclusions) 
- [**Executive Summary**](https://github.com/Kishawn-Dorman/ANOVA-Tests-and-Regression-Modelling#executive-summary-1)
- [**Aim and Objectives**](https://github.com/Kishawn-Dorman/ANOVA-Tests-and-Regression-Modelling#aim-and-objectives-1)
- [**Analysis**](https://github.com/Kishawn-Dorman/ANOVA-Tests-and-Regression-Modelling#analysis-1)
- [**Recommendations**](https://github.com/Kishawn-Dorman/ANOVA-Tests-and-Regression-Modelling#recommendations-1)
- [**Limitations**](https://github.com/Kishawn-Dorman/ANOVA-Tests-and-Regression-Modelling#limitations-1)

[**References**](https://github.com/Kishawn-Dorman/ANOVA-Tests-and-Regression-Modelling#references) 

[**Skills and Tools Used**](https://github.com/Kishawn-Dorman/ANOVA-Tests-and-Regression-Modelling#skills-and-tools-used) 
- [**Libraries Used**](https://github.com/Kishawn-Dorman/ANOVA-Tests-and-Regression-Modelling#libraries=used)

## About the project
Company A is a consultancy firm for schools that recognises that student satisfaction is a KPI for most higher education institutes. Within it there are a range of reasons why students may or may not be satisfied with their courses. The Turkiye Student Evaluation Dataset gives a small insight into the complexities that drive student experience. Using the descriptive analytics, a MANOVA test will be used to indicate the factors significantly impacting student experience.

Company B is a bank seeking data-driven recommendations for its marketing department. The data provided for this analysis is anonymised and constitutes variables relating to a past and recent marketing campaign. Using the predictive analytics a LINEAR and LOGISTIC regression model was built to identify the factors/variables that are great predictors of clients age and if a client has a housing loan.  



## Section 1 - Company A (Descriptive Statistics)

### Objective
The aim of this report is to determine what factor(s) may/may not drive student satisfaction for HigherEdCo Ltd. A data analytical approach will be applied on data from the “Turkiye Student Evaluation” dataset to access the effect of select variables on each other and ultimately on student satisfaction.

##### Dataset Visualization
The “Turkiye Student Evaluation” dataset comprise of 5,820 (observations) student evaluation scores to 28 Likert-scale style questions (variables) and 5 other variables capturing the ‘instr’(instructor type), ‘class’(course type), ‘nb.repeat’ (number of times students took the test), their ‘attendance’ and the perceived ‘difficulty’ of the course by students. 

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/85e7db6f-c6d8-4c7c-90d6-1cfe21d5881f)


Figure 1

Figure 1 above shows that instructor 3 has almost two times (2x) the amount of students than instructor 1 & 2 combined. The credibility of instructor impact in the analysis may be weaken by this because of the unequal instructor groups.

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/d9b1e2cd-e741-417a-97ac-1aafb39e9b84)


Figure 2

Figure 2 above shows that there is an uneven range of student observations per course. The credibility of course (class) impact in the analysis may be weaken by this because of the unequal instructor groups.

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/9b32cca7-33e8-4e7a-9cfa-c4c3e99ea0c3)


Figure 3

Figure 3 above shows that the mean score given by student per question (28 survey questions) is option/answer 3. This suggest the answers may not be an accurate reflection of the student’s opinion. 


### Process
#### Modification of the Dataset
As is the case with most analytical projects working with less variables are ideal for delivering clear and consistent insights. With this in mind the suitability of the 28 survey question variables for a factor analysis was tested using KMO. As shown in the table below all of the variables fall between the KMO range of 0.90 to 1.00 which suggest that the data is excellent for factor analysis.

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/67dfd5f5-a82e-4b88-880d-65f323e2ad07)

Since the variables Q1 to Q28 acted as the measures for student satisfaction, points of correlation was extracted from them using PCA (Principal Component Analysis) and then validated further with parallel analysis. Both of these tests identified 2 components that represent the main areas of focus for the 28 survey questions. In the scree plot diagram below components 1 and 2 both have a higher variance from the other components and a higher correlation to the 28 survey questions, as the elbow curve only begins to flatten at component 3.

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/37ecad52-88d0-40d6-bff4-26afa726514d)


Figure 4

The PCA then generated correlation scores for the 2 components based on the 28 survey questions. A raising out of the scores, component 2 scores correlated highly with Q1 to Q12 and component 1 Q13 to Q28 as shown in the table below.

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/8ed6762e-d6d7-431f-8b76-88f784bb6554)

Based on the questions posed, Q1 to Q12 is focused on course satisfaction and Q13 to Q28 instructor satisfaction.  Both of the components was added to the "TSE Analysed.csv" dataset under the following variable names:
-	Component 1 is “InstrSat”
-	Component 2 is “CourseSat”

The test to follow will look at if the type of instructor and course students are assigned has an effect on student satisfaction as well as how much of an effect and the impact. The aforementioned will be broken up into two hypothesis, a null hypothesis (H0) and an alternative hypothesis (H1). The table below shows the name, classification and category of each variable followed by the two hypothesis.

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/9a7ff029-6095-4f58-b8e8-4e4317935479)

InstrSat, CourseSat ~ Instr * Class
(DV1, DV2 ~ IV1 * IV2)

H0: There is no effect of instr and/or class on InstrSat and CourseSat.
H1: There is an effect of instr and/or class on InstrSat and CourseSat.

### Results
#### Parametric Assumptions:
For this analysis manova test will be used to identify significance if any and for this test a few parametric assumptions need to be met.

##### 1. Normality

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/ae3f75b6-4241-4b15-92e8-2e79a04b2d3a)


Figure 5: InstrSat (DV1)			

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/88758964-7fcf-4712-96ef-caef4c0bc8f5)


Figure 6: CourseSat (DV2)

##### 2. Homogeneity of variance

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/0a72cc91-cb55-4ec5-852d-5c9784893b13)

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/8f030899-79fe-4155-9bf3-5267ea41fc6e)

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/9eb83c38-6294-42c8-aa4d-97411ca3b7c5)

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/bb462c0e-0e37-4df1-857e-12ec1522ccb2)

The parametric assumptions of normality and equal sample group sizes have both been validated and means that hypothesis testing can now commence. 

#### Multivariate Analysis
##### Multivariate ANOVA 
After running the omnibus test, H1 was confirmed, resulting in H0 being rejected. Manova showed a significant main effect of instructor [F(2,5806) = 39.64, p < 0.001, V = 0.03]  and class [F(11,5806) = 11.55, p < 0.001, V = 0.04] on InstrSat and CourseSat. 

Further investigation was carried out by running individual ANOVAs on the DVs. They showed that the results from both the MANOVA and ANOVAs confirmed instructors and courses having an effect on instructor and course satisfaction. However, the effect size (η2) and Pillai-Bartlet trace measurement (V) both indicate that their effect on these two dependent variables (DV) are minor.

DV1 (InstrSat) ANOVA Results:
The result of the ANOVA was significant instr (F[2,5806] = 22.44, p < 0.001, η2 = 0.007) and class (F[11,5806] = 14.66, p < 0.001, η2 = 0.03)  

DV2 (CourseSat) ANOVA Results:
The result of the ANOVA was significant instr (F[2,5806] = 57.29, p < 0.001, η2 = 0.02) and class (F[11,5806] = 8.51, p < 0.001, η2 = 0.03)  

##### Confidence Intervals for Modelled ANOVAs
Confidence intervals plots is another useful tool as it supports the significant results from our ANOVAs tests by visualizing the significant difference of DVs against each IV if any. Figure 7 & 8 show the estimated mean of student scores (InstrSat & CourseSat) for each instructor with a 95% confidence level (meaning that 95/100 the mean student score would fall in this confidence interval). 

Figure 7 below, we found that students under instructor 1 and 3 had the same level of instructor satisfaction, whereas students under instructor 2 had a higher level of instructor satisfaction than instructor 1 & 3.

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/60ee669c-62ee-464c-8e11-fb73b939d0d6)


Figure 7

Figure 8 below, we found that the students from each instructor had different levels of course satisfaction. Students under instructor 1 had the highest level of course satisfaction and students under instructor 3 the lowest level of course satisfaction.

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/8564da4d-9f76-4aa8-8a60-0c2df94dc18a)


Figure 8

Figure 9 & 10 shows the estimated mean of student scores (InstrSat & CourseSat) for each course with a 95% confidence level (meaning that 95/100 the mean student score would fall in this confidence interval). 

For figure 9 below, we found that students shared fairly the same level of instructor satisfaction regardless of the course they were assigned. However, students from course 8 had the highest level of instructor satisfaction in comparison to the other courses.

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/1e968579-75d7-486e-bf9d-640907a4a80e)


Figure 9

For figure 10 below, we found that course satisfaction did vary depending on the course students were assigned. Students from course 2 & 10 had the highest level of course satisfaction in comparison to students from the other courses. However, as seen in figure 2, course 2 may not be very significant because of the difference in sample size when compared to course 10.
 
![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/5041fd15-2cb8-463e-9f9b-82eda5985acc)


Figure 10

##### Tukey Honest Significant Difference (HSD) 

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/dca7b8e6-fa3c-46e1-b39d-d1cdee851bb9)


THSD Result 1

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/580a1ef8-1a2a-4333-8184-0aa37076a35b)


THSD Result 2

Following the results of significance from manova and the individual anovas, a comparison was done on the type of instructors and the type of courses for both DVs using a post-hoc test called Tukey HSD. The exact results can be seen in THSD result 1 and 2. The Tukey HSD test seek to communicate where the significant difference may lie within the significant independent variables.

Based on the post-hoc tests it appears that students assigned to instructor 2 was more satisfied with their instructor than students from other instructors. Students assigned to instructor 1 was more satisfied with their course than students from other instructors.

The post-hoc tests also revealed that students on course 8 was more satisfied with their instructor than students from other courses and students on course 9 & 10 was more satisfied with their course than students on other courses. 


## Section 1 - Results Assessment and Conclusions 
### Executive Summary 
Higher education institutes are built to provide a learning platform for all students. Since learning is the focal point of these institutes, they have a vested interest in assessing their overall effectiveness. It has been revealed that student satisfaction is a KPI for a satisfactory learning platform for most higher education institutes. An analysis of data capturing students’ opinions on a specific educational institution revealed that depending on the type of instructor and/or course a student is assigned, their level of satisfaction with the educational institution can be affected. 

### Aim and Objectives
The aim of the report was to help institutions improve student satisfaction. This was accomplished through the following objectives:
1.	Determining what factors have an effect on student satisfaction and how much of an effect.
2.	Understand which factors have the most significant effect on student satisfaction in comparison to others.

### Analysis
The Turkiye dataset  was used to understand the data and factors that may affect student satisfaction (through firstly statistical charts). They revealed that there was a bit of uneven spread of students across the different courses and instructors of the data. However, with the exception of course 12 there is a minimum average of 100 student observations per course and 750 student observations per instructor. This information helped to add credibility to the relevance of the analysis. 

Before using inferential statistics, the dataset was modified because the large number of student observations captured for the dataset, would have made it challenging to analyse. As a result, to aid the efficiency and reduce the complexity of the analysis, a dimensionality reduction was carried out using a Principal Components Analysis (PCA) and then a parallel analysis test (as second confirmation). Two new factors/variables was formed; instructor & course satisfaction (which together represent student satisfaction).

The inferential statistics method (MANOVA) used, revealed that student satisfaction is affect by the type of instructor and course students' are assigned however, the effect they had were very small according to the dataset.

### Recommendations
Since the analysis results indicate that the type of instructor and the course students are assigned to can have an effect on their overall satisfaction with an institution. To ensure the student satisfaction levels are maintained educational institutions may need to ensure that a good teaching calibre is continuously shown by all instructors at the institution and the tutorial sessions for courses are tailored to the expectations and interests of students.

### Limitations
- The results of this dataset cannot be generalised as meaning the same effects for other educational institutions.
- Outliners issue in normality assumption.
- The data may not be an accurate representation of the opinions of students because of the data collection method (Likert-scale style questions) used.
-	Loss of information because of the dimensionality reduction.




## Section 2 - Company B (Predictive Statistics)

### Objective
Being a part of the finance industry means that the German-Hellenic bank face stiff competition amongst competitors on all fronts. With this in mind, anonymised data of clients was collected for an analysis. The aim of this report is to produce statistical information that can be used by the company’s marketing department to better understand their clients and to build more attractive services for customers. 

##### Dataset Visualization
This data comprise of information for 45,211 (observations) clients, with in it personal demographics, responses and opinions was captured for 17 fields (variables).

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/ab7cec82-6248-4117-973a-add31f130eb6)


Figure 11

The chart above is a visual representation of the age of all clients in the dataset. Based on this chart, it appears that the analysis to follow may be most applicable to middle aged clients as the dataset mostly comprise of clients between 30 to 50 years old.

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/401450d0-3dcb-42b6-9f64-0b77df1b003c)


Figure 12

The chart above is a visual representation of clients with or without a housing loan. It appears that the dataset has a fairly good proportion of both groups of clients. This will aid the statistical power the analysis outcome because of the high number of observations.

### Process
After a visual assessment of the data, variable 12 (duration) captured information and responses that can affect variable 17 (y) and cause there to be a bit of correlation between them. Since this can skew the performance of the model, variable 12 was removed before continuing the analysis. 

##### Multiple Linear Regression Modelling 
Multiple linear regression modelling was chosen because it can help “to make predictions, recognize patterns, and categorize objects” (R, 2021) on the dataset. In preparation for building a model, the data was first tested for any redundant data (this yield no results) and then split into a train (dftrain) and a test dataset (dftest). Although overfitting is unlikely due to the large number of observations (clients) recorded in the dataset, splitting the dataset helps the test to get a realistic evaluation of the model against data that are not a part of the trained data.

Arising out of this split two separate datasets was created; dftrain with 80% & dftest with 20%. A full model was then built with ‘Age’ as the outcome variable and all other variables (except variable 12) as predictors. The model identified numerous predictors that vary in significance. Subsequently, to have the best fitting model for the data, the stepwise method was used to create a final model that has only the most impactful predictors from the full model.

This model was named ‘linstep’ and consist of the following variables
![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/9c991f4a-6def-45dc-b680-d4f054bfd140)

##### Binary Logistic Regression Modelling 
Binary logistic regression modelling was chosen to build the second model around “housing” because it helps to explore the relationship of predictors against the outcome variable (IBM, 2022) and also to access that relationship through probabilities (percentages). The first phase of this method was the same as the linear regression model method with the outcome variable instead being changed to ‘housing’. The final model consisted of the following variables.

This model was named ‘logstep’ and consist of the following variables
![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/de24542a-8b11-43e4-a670-73b9eac4de44)


### Results
Below is a summary of the regression models used.
![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/e83d3337-8301-4e52-b478-9dc40314ffad)

The BIC scores for both model 1 and 2 showcase these stepwise models as being best models in comparison to other. Model 1 was reduced to 9 predictors that explain 42% of the variance in clients’ age and model 2 to 10 predictors that explain 26% of the variance in housing loans on the training sets. Bayes Factor value represents how many times better the model is with fitting the data than the full models.

The linear model was significant overall [F[34,36136] = 761.7, p < 0.001] and the predictors mentioned above for ‘linstep’ are all significant. The logistic model was significant overall and some of the predictors were significant. The t-values for the linear model (linstep) and the z-values for the logistic model (logstep) shows this and can be seen below. 

linstep model significant predictors
![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/e8d3b435-a588-4da5-9092-b9a0dfdb469f)

logstep model significant predictors
![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/2f7c33d5-6b13-4e23-9cd8-f9cce4156b67)


#### Linear Model Predictive Results

As mentioned previously the dataset was split into two, with dftest being unused and the latter used for the model. To access the performance of the linstep model, its predictive ability was tested against unseen data (dftest). Against dftest, the model had an R-squared of 0.42 (same as the linstep model) and the predictions made of clients age was fairly good and in comparison to their actually age.

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/3729e8f9-7b43-4d9e-a16c-34122b2c05e1)

 
Figure 13

The diagram above visualizes the R-squared/performance of the model by plotting the predicted age of clients (predlin) with the actual age of clients (age) in dftest together to form a scatterplot. It also shows a positive linear relationship between predlin and age as the plots converge diagonally with the line of best fit. 

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/e0de2c5f-8e01-4c7b-9b8f-9cb41265a886)

 
Figure 14

The plot above shows that the area of variance is very small which reflects a high r squared. 
This indicates that the model (linstep) built from dftrain was good at predicting client’s age in dftest.

##### Parametric Assumptions:
1.	Homoscedasticity

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/c5d2cd74-3206-4906-aa4f-c90ab936254a)


Figure 15

The scatterplot shows a typical fitted value vs. residual plot in which homoscedasticity is present.

2.	Normality

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/d9a239e9-5a39-4894-adcf-e40c36d96ae8)


Figure 16

The Q-Q plot shows a normal distribution is followed.


#### Logistic Model Predictive Results

For the second model, the dataset was again split into two, with dftest being unused and the latter (dftrain) for the model. Log odds (coefficients) from the model was converted into probabilities. The summary of the probabilities show that generally the type of job, method of contact, the last month of contact and the outcome of the previous marketing campaign decreased the likelihood of a client having a housing loan. However, the variables; jobblue-collar, contactunknown & monthmay greatly increased the likelihood of a client having a housing loan. This can be seen below. 

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/1f2ea1f0-14da-4c59-9afc-0bba874ad9af)

Similar to linstep, the predictive ability of logstep was tested against unseen data (dftest). The predictions made represented the probability of clients having a housing loan. These predictions were quite good and can be found in the “BMC Analysed.csv” dataset.

A confusion matrix is a great tool as it reflects a summative table of the correct and incorrect predictions made. But, before deriving the final confusion matrix table a roc curve chart was created to determine the best cut-off point for a more sensitive matrix. 

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/a26f9fad-14d2-46f5-a47f-a89942bd4994)


Figure 17

The chart above is a roc-curve of the outcome variable in the test set. The higher the point is on the y-axis, the more precisely it will (Vadakkanmarveettil, 2015) “measure the proportion of actual positives which are correctly identified” in the confusion matrix. Based on the chart above using 0.4 as the cut-off point will increase the amount of positive predictions. Since the aim of this analysis is to determine what variables can make the most accurate predictions for clients’ age, having a more sensitive matrix will align with this aim and can be seen in table below.

##### Confusion Matrix

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/f2e62d37-e1bb-415a-910b-1f78ea0dcfd2)


0 = clients without a housing loan	TN = True Negative	FP = False Positive
1 = clients with a housing loan	FN = False Negative	TP = True Positive


Finally statistical measures was executed to show the model’s performance.

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/46960e95-aeb9-4fab-8ac7-47b6c8e6f4cf)


##### Parametric Assumptions:

1.	Multicollinearity 
VIF values for the predictors in the logstep model are all less than 5, which means that there is no significant relationship between the predictors.

2.	Extreme Outliners

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/643fd988-e0a8-46bf-afe7-deb23408ce7c)

 
There are outliners however, they are not extreme.


## Section 2 - Results Assessment and Conclusions
### Executive summary
Businesses around the world are constantly seeking progressive improvements in the way they carry out business. Data-driven research have been found to be one of the most effective ways to help compose effective strategies in all aspects of a business. For this reason an analysis was carried out on data containing client information for a bank. 

Arising out of the analysis, a few factors that capture clients’ personal demographics, previous and present campaign information and clients’ opinions stood out as being great predictors of clients’ age and housing loan status. For the bank understanding them can help it’s marketing team re-evaluate their product/service approach and their strategic objectives.

### Aim and Objectives
The aim of the report is to derive useful data for the bank using a data-driven analysis. This was accomplished through the following objectives:
1.	Determine what factors can significantly predict the age of clients and whether or not clients have a housing loan.
2.	Gauge the performance of these factors when making predictions.

### Analysis
The data used for the analysis featured a substantial amount of client information and as with any analysis having a large amount of data is ideal. The analysis commenced by testing the predictive ability of all other the factors in the dataset provided against clients age and their housing loan status (separately).  For clients age; job, marital status, educational background, account balance, housing loan status, contact method used, month contacted and clients’ opinion of the previous marketing campaign when modelled together appear to be a good predictor of clients’ age. These factors/predictors accounted for 42% of the predictability element of clients’ age.

In the case of the housing loan status of clients; age, type of job, marital status, educational background, account balance, contact method used, day of last contact, month contacted, contacts during the present campaign, days post contact and clients’ opinion of the previous marketing campaign when modelled together appear to be a good predictor of clients’ housing loan status. In further accessing the predictors of clients’ housing loan status probabilities of housing loan’s response to increases and decreases to the predictors was captured.

The summary of the probabilities show that primarily the type of job, method of contact, the last month of contact and the outcome of the previous marketing campaign decreased the likelihood of a client having a housing loan. However, clients in blue-collar jobs, contacted with an unknown method and/or during the month of May greatly increased the likelihood of a client having a housing loan. 

### Recommendations
The analysis results revealed that there are quite a few factors that can act as predictors for clients’ age and housing loan status as mentioned previously.  With this in mind, The bank's marketing department should make their goods/services more appealing to clients by being more strategic and specific about the clients to be targeted for marketing campaigns, products, offers and/or promotions. 

The analysis has also revealed that external elements like the month and day should most certainly be consider as they were both proven to be significant predictors to determining what kind clients are engaged. For example, a house loan promotion with low interest rates for clients under 30 years old can be ran at the end of the month. This would attract clients in blue-collar jobs because of its availability (as these clients typically receive their salary around that time) and because the majority of clients at this bank is under 30 years based on the data. 

### Limitations
- The significance of the test may become biased as the p-value maybe affected by the normality issue.
- Linear correlation between independent variables (predictors) diminish their predictive power.
- The data collected could be inaccurate or outdated which would skew the outcome of the analysis.


## References
Gunduz, G. & Fokoue, E. (2013). UCI Machine Learning Repository 
[[https://archive.ics.uci.edu]]. Irvine, CA: University of California, School of Information and Computer Science.

S. Moro, P. Cortez and P. Rita. A Data-Driven Approach to Predict the Success of Bank
Telemarketing. Decision Support Systems, Elsevier, 62:22-31, June 2014

R, S., 2021. Data Flare Up. [Online] 
Available at: https://www.dataflareup.com/why-use-linear-regression-models-instead-of-neural-networks/
[Accessed 22 December 2022].

IBM, 2022. What is logistic regression? [Online] 
Available at: https://www.ibm.com/topics/logistic-regression
[Accessed 22 December 2022].

Vadakkanmarveettil, J., 2015. Sensitivity vs. Specificity in Logistic Regression. [Online] 
Available at: https://www.jigsawacademy.com/sensitivity-vs-specificity-in-logistic-regression/
[Accessed 03 January 2023].

## Skills and tools used
- Exploratory Data Analysis (PCA, Univariate analysis, Bivariate analysis)
- Descriptive Analytics
- Predictive Analytics
- Prescriptive Analytics
- R

### Libraries used
- Psych
- caret
- ggplot2
- Paran
- lsr
- verfication
- car
- sjplot
- stats

## Want to connect/have a question? 
[Linkedin](https://www.linkedin.com/in/kishawndorman/)

