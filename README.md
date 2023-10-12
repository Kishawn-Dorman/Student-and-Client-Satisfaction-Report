# Business-Data-Analytics-Project
In this project, recommendations and insights are generated by firstly using exploratory data analysis on the "Turkiye Student Evaluation(TSE)" dataset [can be found here](https://archive.ics.uci.edu/dataset/262/turkiye+student+evaluation) and "Bank Marketing Campaign(BMC)" dataset [can be found here](https://archive.ics.uci.edu/dataset/222/bank+marketing). 

I then apply descriptive analytics to TSE, predictive analytics to BMC and lastly prescriptive analytics on the results generated from both datasets to provide some insight and recommendations of actions a school (TSE dataset) and a bank (BMC dataset) can take up for improvement.

## About the project
As part of my business data analytics MSc module, I was tasked with analysing data for two companies. Company A is a consultancy firm for schools that recognises that student satisfaction is a KPI for most higher education institutes. Within it there are a range of reasons why students may or may not be satisfied with their courses. The Turkiye Student Evaluation Dataset gives a small insight into the complexities that drive student experience. Using the descriptive analytics, a MANOVA test will be used to indicate the factors significantly impacting student experience.

Company B is a bank seeking data-driven recommendations for its marketing department. The data provided for this analysis is anonymised and constitutes variables relating to a past and recent marketing campaign. Using the predictive analytics a LINEAR and LOGISTIC regression model was built to identify the factors/variables that are great predictors of clients age and if a client has a housing loan.  

## Section 1 - Company A (Descriptive Statistics)

### Introduction
The aim of this report is to determine what factor(s) may/may not drive student satisfaction for HigherEdCo Ltd. A data analytical approach will be applied on data from the “Turkiye Student Evaluation” dataset to access the effect of select variables on each other and ultimately on student satisfaction.

##### Dataset Details 
The “Turkiye Student Evaluation” dataset comprise of 5,820 (observations) student evaluation scores to 28 Likert-scale style questions (variables) and 5 other variables capturing the ‘instr’(instructor type), ‘class’(course type), ‘nb.repeat’ (number of times students took the test), their ‘attendance’ and the perceived ‘difficulty’ of the course by students. 

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/85e7db6f-c6d8-4c7c-90d6-1cfe21d5881f)
 
Figure 1
Figure 1 shows that instructor 3 has almost two times (2x) the amount of students than instructor 1 & 2 combined. The credibility of instructor impact in the analysis may be weaken by this because of the unequal instructor groups.

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/d9b1e2cd-e741-417a-97ac-1aafb39e9b84)

Figure 2
Figure 2 shows that there is an uneven range of student observations per course. The credibility of course (class) impact in the analysis may be weaken by this because of the unequal instructor groups.

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/9b32cca7-33e8-4e7a-9cfa-c4c3e99ea0c3)

Figure 3
Figure 3 shows that the mean score given by student per question (28 survey questions) is option/answer 3. This suggest the answers may not be an accurate reflection of the student’s opinion. 


### Process
#### Modification of the Dataset
Since the variables Q1 to Q28 acted as the measures for student satisfaction, points of correlation was extracted from them using PCA (Principal Component Analysis) and then validated further with parallel analysis. Both of these tests identified 2 components that represent the main areas of focus for the 28 survey questions. In the scree plot diagram below components 1 and 2 both have a higher variance from the other components and a higher correlation to the 28 survey questions, as the elbow curve only begins to flatten at component 3.

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/37ecad52-88d0-40d6-bff4-26afa726514d)

Figure 4
The PCA then generated correlation scores for the 2 components based on the 28 survey questions. A raising out of the scores, component 2 scores correlated highly with Q1 to Q12 and component 1 Q13 to Q28. Based on the questions posed, Q1 to Q12 is focused on course satisfaction and Q13 to Q28 instructor satisfaction.  Both of the components was added to the dataset under the following variable names:
-	Component 1 is “InstrSat”
-	Component 2 is “CourseSat”

The test to follow will look at if the type of instructor and course students are assigned has an effect on student satisfaction as well as how much of an effect and the impact. The aforementioned will be broken up into two hypothesis, a null hypothesis (H0) and an alternative hypothesis (H1). The table below shows the name, classification and category of each variable followed by the two hypothesis.

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/9a7ff029-6095-4f58-b8e8-4e4317935479)

InstrSat, CourseSat ~ Instr*Class
(DV1, DV2 ~ IV1*IV2)

H0: There is no effect of instr and/or class on InstrSat and CourseSat.
H1: There is an effect of instr and/or class on InstrSat and CourseSat.

### Results
#### Parametric Assumptions:
For this analysis manova test will be used to identify significance if any and for this test a few parametric assumptions need to be met.

##### 1. Normality
The QQ plots below depicts points of InstrSat and CourseSat scores in a fairly straight line. The x-axis plots the theoretical quantiles with a mean 0 and standard deviation 2. At glance our assumptions of InstrSat and CourseSat scores all coming from a population that is normally distributed is fairly good.

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/ae3f75b6-4241-4b15-92e8-2e79a04b2d3a)

Diagram 1: InstrSat (DV1)			
Figure 5					

![image](https://github.com/Kishawn-Dorman/Business-Data-Analytics-Project/assets/146044118/88758964-7fcf-4712-96ef-caef4c0bc8f5)

Diagram 2: CourseSat (DV2)
Figure 6

##### 2. Homogeneity of variance
Boxplots (refer to appendix 3) was used to test homogeneity of the sample groups because the scores for both dependent variables are in the form of ordinal data. The boxplots showed that the sample groups’ sizes for the independent variables do not appear to be vastly unequal. This is a good sign and means that the sample groups are homogeneous the power of our test may not necessarily be decreased by biased results (a skewed F-statistic). 

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

For figure 7, we found that students under instructor 1 and 3 had the same level of instructor satisfaction, whereas students under instructor 2 had a higher level of instructor satisfaction than instructor 1 & 3.

 
Figure 7

For figure 8, we found that the students from each instructor had different levels of course satisfaction. Students under instructor 1 had the highest level of course satisfaction and students under instructor 3 the lowest level of course satisfaction.

 
Figure 8





Figure 9 & 10 show the estimated mean of student scores (InstrSat & CourseSat) for each course with a 95% confidence level (meaning that 95/100 the mean student score would fall in this confidence interval). 

For figure 9 we found that students shared fairly the same level of instructor satisfaction regardless of the course they were assigned. However, students from course 8 had the highest level of instructor satisfaction in comparison to the other courses.

 
Figure 9

For figure 10, we found that course satisfaction did vary depending on the course students were assigned. Students from course 2 & 10 had the highest level of course satisfaction in comparison to students from the other courses. However, as seen in figure 2, course 2 may not be very significant because of the difference in sample size when compared to course 10.
 
Figure 10

##### Tukey Honest Significant Difference (HSD) 
Following the results of significance from manova and the individual anovas, a comparison was done on the type of instructors and the type of courses for both DVs using a post-hoc test called Tukey HSD. The exact results can be found in appendix 1 and 2. The Tukey HSD test seek to communicate where the significant difference may lie within the significant independent variables..
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


## Skills and tools used
- Exploratory Data Analysis (PCA, Univariate analysis, Bivariate analysis)
- Descriptive Analytics
- Predictive Analytics
- Prescriptive Analytics
- R

## Libraries used
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

