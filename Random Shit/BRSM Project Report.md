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
- 