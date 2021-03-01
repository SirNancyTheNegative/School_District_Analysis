# PyCitySchools with Pandas

## Overview of Project

### Purpose

In this project, we analyze the reported grades of students from fifteen different high schools within the district. We are given two CSV files: One containing all the data pertaining to the fifteen schools (e.g.s budget, population, and whether or not it's a charter school), and the other with all of the data pertaining to the students, including grades for both math and reading. As such, it is our duty to determine the average passing rates of the district as a whole, as well as for each school, in order to determine which schools in the district are the best and the worst. We also determine how the grades within each school fare, and then determine how well (or how poorly) students do in schools with different spending ranges, population sizes, and the difference in scores between charter schools and district schools. 

However, there was a case of academic dishonesty: The freshmen of Thomas High School had their grades altered, but we do not know to what extent. This wasn't brought to our attention until after we had done preliminary  It is, then, our job to remove the scores listed for all Thomas High School freshmen, as to try and uphold the usual state-testing standards, and the true purpose of this project is to assess the scale of error that the removal of said forged grades will fix.

## Results

### Foreword

It's worth noting that, in order to solve the conundrum of the forged grades, counts of the student population for the purposes of determining percentages of passing students have also had to be altered. It wouldn't do to simply remove the Thomas High School freshmen from the DataFrame -- they still exist, it's just that only their grades must be removed for legitimacy concerns.

### District Analysis

When considering the district as a whole, the methods with which we determine the district's standards are mostly the same -- as said above, only the 9th graders from Thomas High School are not factored into the calculations. 
With the grades intact as they were, these are the results we procured from the data.

![The frame containing averages for passing marks before removing the Thomas High School freshman scores](https://github.com/SirNancyTheNegative/School_District_Analysis/tree/main/Resources/Images/District_Before.png)

And here is the district results with the Thomas High School freshman grades scrubbed.

![The frame containing averages for passing marks after removing the offending scores](https://github.com/SirNancyTheNegative/School_District_Analysis/tree/main/Resources/Images/District_After.png)

With the offending grades removed, very little changed. The only minor differences between the two are:

* The student count was reduced by 461, the number of Thomas High School freshmen whose scores were scrubbed.
* The average math score for the district dropped by 0.1 points.

It is too soon to say that the results lead to any real conclusion -- the entire district consists of over 39,000 students, and 461 students makes up only a little more than 1% of the district. If we look at the other partitions, perhaps we'll get a clearer view of the impact the removal of those scores might have.

### School Analysis

By partitioning the district's students into their respective schools, we can further single out Thomas High School students to determine if the change is significant enough to consider. 

![The frame containing each school's passing rates before removing THS freshman scores](https://github.com/SirNancyTheNegative/School_District_Analysis/tree/main/Resources/Images/Schools_Before.png)

![The frame containing each school's passing rates after removing THS freshman scores](https://github.com/SirNancyTheNegative/School_District_Analysis/tree/main/Resources/Images/Schools_After.png)

The differences exist primarily within Thomas High School's entry, as one might expect, and they are, from before removing the scores to after removing the scores:
* A decrease of 0.067 points on the average math score
* An increase of 0.047 points on the average reading score
* A decrease to the % Passing Math of about 0.086
* A decrease to the % Passing Reading of about 0.29
* A decrease to the % Overall Passing of about 0.32

Considering we know there are 461 freshman students in Thomas High School, the notable changes here are the decrease in the percent of the student body passing. If we take the decreases to % Passing Reading and % Overall Passing and apply it to the 461 students, we find that on average, 1.33 students are no longer passing reading, and 1.48 students are no longer passing altogether. What this means is, there is likely correlation between at least one freshman artificially modifying their grades, and the fact that the decrease of % Overall Passing is higher in magnitude than the decrease of % Passing Reading suggests that it might have been done to at least two students, though that might be circumstantial conjecture. The decrease of the math score, on the other hand, is too low to reasonably show any correlation between a noticeable effect with the district averages, leading us to believe that it to be merely an issue with rounding, though it is worth noting that Thomas High School's scores remain higher than the district's standards before and after the freshman scores have been removed.

### Thomas High School's Performance

Before we consider that this might be done by faculty in an effort to boost their outwards performance among the other districts, it's important to see if there was any shift to the rankings of Thomas High School with respect to the other schools in the district. As such, ranked by % Overall Passing, here is ![The ranking of Thomas High School before removing THS freshman scores](https://github.com/SirNancyTheNegative/School_District_Analysis/tree/main/Resources/Images/Rankings_Before.png), and here is ![The ranking of Thomas High School after removing freshman scores](https://github.com/SirNancyTheNegative/School_District_Analysis/tree/main/Resources/Images/Rankings_After.png).

In both circumstances, Thomas High School is in second place, though after removing the offending scores, when compared to Griffin High School, it looks as though it could be overtaken with just a handful more passing grades. This is likely circumstantial, though the possibility that Thomas High School's faculty might be made aware of this information if it has been introduced to them previously.

### Further Partitioning

In our original analysis we further partitioned the data by grade, by grouping the schools by spending per capita, by school size, and by school type in order to see how those demographics compared with one another. Once more, to account for the replacement of the Thomas High School freshman scores, we have re-assessed the schools through those categories.

* Because we separate the average scores for each grade along school lines, the only change possible is the scores for THS freshman. ![Suffice to say](https://github.com/SirNancyTheNegative/School_District_Analysis/tree/main/Resources/Images/Grade_math_before.png), they've been ![replaced with NaN](https://github.com/SirNancyTheNegative/School_District_Analysis/tree/main/Resources/Images/Grade_math_after.png).
* When analyzing the data through how much each school spends per capita, there is not a significant difference between [the results before THS's freshman scores were removed](https://github.com/SirNancyTheNegative/School_District_Analysis/tree/main/Resources/Images/Spending_before.png) and [the results after](https://github.com/SirNancyTheNegative/School_District_Analysis/tree/main/Resources/Images/Spending_after.png). It's worth noting that Thomas High School exists in the "$630 to $644" bin.
* Similarly, there isn't a noticeable difference when splitting them by population. Thomas High School is in the "1000 to 2000" bin, and both [before](https://github.com/SirNancyTheNegative/School_District_Analysis/tree/main/Resources/Images/Size_before.png) and [after](https://github.com/SirNancyTheNegative/School_District_Analysis/tree/main/Resources/Images/Size_before.png) removing THS freshman grades, the difference isn't enough to appear in the dataframe.
* Finally, there is no change in what's shown in the dataframe [before](https://github.com/SirNancyTheNegative/School_District_Analysis/tree/main/Resources/Images/Type_before.png) and [after](https://github.com/SirNancyTheNegative/School_District_Analysis/tree/main/Resources/Images/Type_after.png) THS's freshman grades were removed.

## Summary

### What does it mean?

There are only really a few changes between the analysis before and after the Thomas High School freshman scores were removed. The first important one is the decrease of the average math score centered at Thomas High School. A decrease of 0.067 points on average doesn't say too much, but it does indicate that, if someone were tampering with their scores, they were aiming for higher than passing. Second, the % Passing Math of Thomas High School decreased by 0.086%, suggesting that if the tampering were to have happened with Math scores, it was done to a small number of students. Third, the % Passing Reading of Thomas High School decreased by 0.29%. This indicates that there were overall more issues with reading among the freshmen than there were in Math, but the most puzzling one is the fourth: The increase of average reading scores after the freshman scores were dropped. Coupled with the decreased passing rate, this suggests that instead of perhaps a single student artificially increasing their math scores to substantially higher scores, there may have perhaps been a handful of freshmen whose scores were changed to be above passing, but not spectacular. This makes sense: To be outstanding means to stand out. If you're cheating, you don't want to bring attention to the fact that you're cheating. The same principle applies here -- it would be far easier for someone to fudge enough reading scores to be good enough to pass than it would be if those scores were to be made outstanding.
