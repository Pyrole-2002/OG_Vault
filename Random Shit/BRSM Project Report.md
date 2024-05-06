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
#### Shapiro test for Age
![[Pasted image 20240506132646.png]]
![[Pasted image 20240506132704.png]]
#### Gender
![[Pasted image 20240506132759.png]]
#### Address
![[Pasted image 20240506132821.png]]
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
#### Guardian
![[Pasted image 20240506133341.png]]
#### Travel Time
![[Pasted image 20240506133402.png]]
#### Study Time
![[Pasted image 20240506133433.png]]
#### Failures
![[Pasted image 20240506133509.png]]
#### Extra Educational Support
![[Pasted image 20240506133536.png]]
#### Family Education Support
![[Pasted image 20240506133603.png]]
#### Paid Classes
![[Pasted image 20240506133617.png]]
#### Extra-Curricular Activities
![[Pasted image 20240506133644.png]]
#### Nursery
![[Pasted image 20240506133658.png]]
#### Higher Education
![[Pasted image 20240506133718.png]]
#### Internet Access
![[Pasted image 20240506133734.png]]
#### Romantic Relationship
![[Pasted image 20240506133753.png]]
#### Family Relationship
![[Pasted image 20240506133813.png]]
#### Free Time
![[Pasted image 20240506133827.png]]
#### Going Out
![[Pasted image 20240506133841.png]]
#### Workday Alcohol Consumption
![[Pasted image 20240506133858.png]]
#### Weekend Alcohol Consumption
![[Pasted image 20240506133921.png]]
#### Health
![[Pasted image 20240506133942.png]]
#### Absences
![[Pasted image 20240506133954.png]]
#### G1
![[Pasted image 20240506134026.png]]
#### G2
![[Pasted image 20240506134037.png]]
#### G3
![[Pasted image 20240506134046.png]]

---
