# Team Name
##### Name: Aryan Bansal
##### Roll Number: 2021111018
## Dataset Introduction
###### Source: [Dataset Link](https://archive.ics.uci.edu/dataset/320/student+performance)
- The dataset pertains to student achievement in secondary education and encompasses information from two Portuguese schools. It was gathered through the utilization of school reports and questionnaires, capturing a variety of attributes including student grades, demographic details, social factors, and school-related features.
- Two distinct datasets are provided, each focusing on the performance in a specific subject: Mathematics (mat) and Portuguese language (por).
- In the study conducted by Cortez and Silva in 2008, the datasets were structured to facilitate binary and five-level classification as well as regression tasks.
- An important observation highlighted in the study is the strong correlation of the target attribute, G3, with attributes G2 and G1. This correlation arises due to the fact that G3 represents the final year grade issued during the 3rd period, while G1 and G2 correspond to grades from the 1st and 2nd periods respectively. It is noted that predicting G3 without considering G2 and G1 is challenging, yet such prediction holds significant utility, as detailed in the referenced paper.

| Variable Name |                                           Description |
| :------------ | ----------------------------------------------------: |
| school        |                             Student's school (binary) |
| sex           |                                Student's sex (binary) |
| age           |                                Students age (numeric) |
| address       |                               Urban or Rural (binary) |
| famsize       |                             Family size (categorical) |
| Pstatus       |                 Parent's cohabitation status (binary) |
| Medu          |                      Mother's education (categorical) |
| Fedu          |                      Father's education (categorical) |
| Mjob          |                            Mother's Job (categorical) |
| Fjob          |                            Father's Job (categorical) |
| reason        |            Reason to choose this school (categorical) |
| guardian      |                      Student's guardian (categorical) |
| traveltiime   |               Hme to school travel time (categorical) |
| studytime     |                       Weekly study time (categorical) |
| failures      |               Number of past class failures (numeric) |
| schoolsup     |                    Extra educational support (binary) |
| famsup        |                     Family education support (binary) |
| paid          | Extra paid classes within the course subject (binary) |
| activities    |                  Extra-curricular activities (binary) |
| nursery       |                      Attended nursery school (binary) |
| higher        |               Wants to take higher education (binary) |
| internet      |                      Internet access at home (binary) |
| romantic      |                   In a romantic relationship (binary) |
| famrel        |       Quality of family relatiioinships (categorical) |
| freetime      |                  Free time after school (categorical) |
| goout         |                  Going out with friends (categorical) |
| Dalc          |             Workday alcohol consumption (categorical) |
| Walc          |             Weekend alcohol consumption (categorical) |
| health        |                   Current health status (categorical) |
| absences      |               Number of school absences (categorical) |
| G1            |                          First period grade (numeric) |
| G2            |                         Second period grade (numeric) |
| G3            |                                 Final grade (numeric) |
### Ambiguities
- The dataset comprises grades for two core courses, Mathematics and Portuguese, both mandatory for all students.
- The Mathematics dataset includes information from 395 distinct students, lacking individual student identification.
- The Portuguese dataset encompasses data from 649 distinct students, also without student identification.
- The authors of the dataset and associated research paper provided an R script to merge the datasets and identify common students taking both courses.
- According to the merging script, two students are considered identical if they share the same values for specific variables: school, sex, age, address, famsize, Pstatus, Medu, Fedu, Mjob, Fjob, reason, nursery, and internet.
- However, it's possible that distinct students could share identical values for these variables, raising concerns about the accuracy of the merging process.
- Additionally, the merging script does not account for other variables such as guardian, traveltime, activities, romantic, famrel, freetime, goout, Dalc, Walc, health, and absences, which can significantly influence the results.
- Due to the absence of a unique student identification ID, it's safest to conduct statistical tests only on the Portuguese dataset to avoid potential inaccuracies in merging and analysis.
## Distribution of Data
#### School
![[Pasted image 20240506132141.png]]
The two schools from which data was collected were named GP and MS, with GP having significantly more students than MS in the dataset.
#### Shapiro test for Age
![[Pasted image 20240506132646.png]]
The shapiro test for normality shows that age isn't normally distributed. The same can be verified from the age distribution plot below.
![[Pasted image 20240506132704.png]]
#### Gender
![[Pasted image 20240506132759.png]]
Majority of participants were Female.
#### Address
![[Pasted image 20240506132821.png]]
Majority of students resided in urban areas.
#### Family Size
![[Pasted image 20240506132901.png]]
#### Parent's Cohabitation Status
![[Pasted image 20240506132930.png]]
#### Mother's Education
![[Pasted image 20240506132958.png]]
#### Father's Education
![[Pasted image 20240506133027.png]]
#### Mother's Job
![[Pasted image 20240506133106.png]]![[Pasted image 20240506133121.png]]
#### Father's Job
![[Pasted image 20240506133143.png]]
#### Reason to chose school
![[Pasted image 20240506133204.png]]
We can see that the most common reason to chose the specific school was the proximity to the students home.
#### Guardian
![[Pasted image 20240506133341.png]]
A large proportion of students had their mother as their guardian.
#### Travel Time
![[Pasted image 20240506133402.png]]
Majority of students had very little travel time to school (< 30 min), this is also supported by the distribution of reason to choose that school.
#### Study Time
![[Pasted image 20240506133433.png]]
#### Failures
![[Pasted image 20240506133509.png]]
Most students have 0 failures.
#### Extra Educational Support
![[Pasted image 20240506133536.png]]
Most students take extra educational support.
#### Family Education Support
![[Pasted image 20240506133603.png]]
A decent portion of the students don't have family education support, however majority students do.
#### Paid Classes
![[Pasted image 20240506133617.png]]
Almost all students take paid classes.
#### Extra-Curricular Activities
![[Pasted image 20240506133644.png]]
Approximately half of the students don't take part in extra-curricular actvities.
#### Nursery
![[Pasted image 20240506133658.png]]
Majority of the students took nursery in childhood.
#### Higher Education
![[Pasted image 20240506133718.png]]
A large proportion of the students want to take higher education in future.
#### Internet Access
![[Pasted image 20240506133734.png]]
Majority of the students have access to internet.
#### Romantic Relationship
![[Pasted image 20240506133753.png]]
More than half of the students are engaged in romantic relationships.
#### Family Relationship
![[Pasted image 20240506133813.png]]
#### Free Time
![[Pasted image 20240506133827.png]]
#### Going Out
![[Pasted image 20240506133841.png]]
#### Workday Alcohol Consumption
![[Pasted image 20240506133858.png]]
Majority of students don't consume alcohol on weekdays or consume very less.
#### Weekend Alcohol Consumption
![[Pasted image 20240506133921.png]]
#### Health
![[Pasted image 20240506133942.png]]
#### Absences
![[Pasted image 20240506133954.png]]
Interesting pattern we see here is that the number of odd absences are significantly more than their corresponding neighboring even absences.
#### G1
![[Pasted image 20240506134026.png]]
#### G2
![[Pasted image 20240506134037.png]]
#### G3
![[Pasted image 20240506134046.png]]

---
## Correlation Heatmap
![[Pasted image 20240506140734.png]]
- Mother's Education and Father's Education are highly correlated.
- G1, G2, G3 are highly correlated with each other and negatively correlated to number of failures which is intuitive.
- Weekend and Weekday alcohol consumption are highly correlated and also correlated to how much student goes to hangouts.
## PCA Scree Plot
![[Pasted image 20240506140840.png]]![[Pasted image 20240506140856.png]]
The first two principle components explain large fraction of the variance.
## Factor Analysis
![[Pasted image 20240506140923.png]]![[Pasted image 20240506140938.png]]

---
## Hypothesis Testing
$$H_A: \text{Students who have internet access at home have higher scores (G3) than students who do not have internet access at home}$$
$$H_0: \text{There is no difference in the scores (G3) between students who have internet access at home and students who do not have internet access at home.}$$
> [!tip] Note
> I have tested the hypothesis separately for each school, continuing what Ashmit showed in his analysis that the grade distribution of the two schools is different.
