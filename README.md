![Header](/pics/header.png)

#### Table of Contents

[Project Overview](#project-overview)  
[Resources](#resources)  
[Objectives](#objectives)  
[Summary](#summary)  
[Challenge Overview](#challenge-overview)  
[Challenge Objectives](#challenge-objectives)  
[Challenge Summary](#challenge-summary)  
[Limitations](#limitations)

## Project Overview
In R-Analysis, we applied our understanding of statistics and hypothesis testing to analyze a series of datasets from the automotive industry. Our analysis includes visualizations, statistical tests, and interpretation of the results. All of our statistical analysis and visualizations are written in the R programming language.  

Throughout the module, we extract, transform, and load (ETL) data; visualize the data; and analyze the data using R. Additionally, we learned a variety of statistical tests, their real-world application in data science, and their implementation in R.  

## Resources  
- **Data Source:** [demo.csv](), [demo.json](), [demo2.csv](), [mpg_modified](), [used_car_data](), [Vehicle_Data](), [MechaCar_mpg.csv](), [Suspension_coil.csv]() 
- **Software:** R, RStudio, Rtools

## Objectives
- Load, clean up, and reshape datasets using tidyverse in R.
- Visualize datasets with basic plots such as line, bar, and scatter plots using ggplot2.
- Generate and interpret more complex plots such as boxplots and heatmaps using ggplot2.
- Plot and identify distribution characteristics of a given dataset.
- Formulate null and alternative hypothesis tests for a given data problem.
- Implement and evaluate simple linear regression and multiple linear regression models for a given dataset.
- Implement and evaluate the one-sample t-Tests, two-sample t-Tests, and analysis of variance (ANOVA) models for a given dataset.
- Implement and evaluate a chi-squared test for a given dataset.
- Identify key characteristics of A/B and A/A testing.
- Determine the most appropriate statistical test for a given hypothesis and dataset.

## Summary  
### Load, clean up, and reshape datasets using tidyverse in R.  
The **tidyverse** package contains libraries such as dplyr, tidyr, and ggplot2. These packages work together to help simplify the process of creating transformed data columns, grouping data using factors, reshaping our two-dimensional data structures, and visualizing our results using plots.  
#### Load  
To install the tidyverse in our R environment, run the following command in the R console:  
> install.packages("tidyverse")  

Raw data is often insufficient in telling the full story. Usually when we are analyzing data, we want to perform calculations and incorporate the calculations back into the raw data to ease in downstream analysis. Tidyverse’s dplyr library transforms R data.  
> library(tidyverse)

#### Clean up  
The dplyr library contains a wide variety of functions that can be chained together to transform data quickly and easily. By chaining functions together, the user does not need to assign intermediate vectors and tables. Instead, all of the data transformation can be performed in a single assignment function that is easy to read and interpret.  

- **mutate()** transforms a data frame and include new calculated data columns.  

- **group_by()** tells dplyr which factor (or list of factors in order) to group our data frame by.  

- **summarize()** creates columns in our summary data frame and will use statistics summary functions such as mean(), median(), sd(), min(), max(), and n().

**mutate()**  

<img align="left" width="500" src="/pics/mutate_function.png"><br/>  
<br/>
<br/>
<br/>
<br/>  
<br/>

**group_by()**  

<img align="left" width="300" src="/pics/group_by_function.png"><br/>  
<br/>
<br/>
<br/>
<br/>  
<br/>
<br/>
<br/>
<br/>  

**summarize()**  

<img align="left" width="500" src="/pics/summarize_function.png"><br/>
<br/>
<br/>
<br/>
<br/>  
<br/>
<br/>
<br/>  
<br/>
<br/>

#### Reshape
When performing more involved data analytics and visualizations, there may be situations where the shape and design of our data frame is overcomplicated or incompatible with the libraries and functions we wish to use. The tidyr library from the tidyverse has the gather() and spread() functions to help reshape our data.  

- **gather()** changes the dataset to a long format.  

- **spread()** spreads out a variable column of multiple measurements into columns for each variable.  

**gather()**  

<img align="left" width="200" src="/pics/gather_function.png"><br/>  

**spread()**  

<img align="left" width="500" src="/pics/spread_function.png"><br/>  
<br/>
<br/>
<br/>
<br/>  
<br/>
<br/>  
<br/>  

### Visualize datasets with basic plots such as line, bar, and scatter plots using ggplot2.  
<img align="left" width="250" src="/pics/line.png"><br/>  

<img align="left" width="250" src="/pics/bar.png"><br/>  

<img align="left" width="250" src="/pics/scatter.png"><br/>
<br/>
<br/>
<br/>
<br/>  
<br/>
<br/>
<br/>
<br/>  
<br/>
<br/>
<br/>
<br/>

### Generate and interpret more complex plots such as boxplots and heatmaps using ggplot2.  
<img align="left" width="250" src="/pics/boxplot.png"><br/>  
<img align="left" width="250" src="/pics/heatmap.png"><br/>  
<br/>
<br/>
<br/>
<br/>
<br/>  
<br/>
<br/>
<br/>
<br/> 

### Plot and identify distribution characteristics of a given dataset.  
When it comes to data analysis, characterizing the distribution of numerical data is as important as characterizing the different data types.  

Normal distribution, or normality, is commonly referred to as “the bell curve,” and describes a dataset where values farther from its mean occur less frequently than values closer to its mean.  The **qualitative test for normality** is a visual assessment of the distribution of data, which looks for the characteristic bell curve shape across the distribution.  

The **quantitative test for normality** uses a statistical test to quantify the probability of whether or not the test data came from a normally distributed dataset. In most cases, data scientists will use the Shapiro-Wilk test for normality, though there are many other statistical tests available. The **shapiro.test()** function only requires the numeric vector of values you wish to test. If the p-value is greater than 0.05, the data is considered normally distributed. 

When the asymmetrical distribution has one distribution tail that is longer than the other, this is commonly referred to as a **skewed distribution** and there are two types—left skew and right skew.  
- A data distribution is considered to be **left skewed**, or negative skewed, if the left tail is longer than the right. Left skewed data has a higher probability that extreme negative values exist within the dataset.  

- A data distribution is considered to be **right skewed**, or positive skewed, if the right tail is longer than the left. Right skewed data has a higher probability that extreme positive values exist within the dataset. 


### Formulate null and alternative hypothesis tests for a given data problem.  
One of the largest and most critical concepts in statistics is hypothesis testing. In data science, we use statistical hypothesis testing to determine the probability of an event (or set of observations) under particular assumptions. There are two types of statistical hypothesis:
- The null hypothesis is also known as H0 and is generally the hypothesis that can be explained by random chance.

- The alternate hypothesis is also known as Ha and is generally the hypothesis that is influenced by non-random events.  

Hypothesis testing uses five steps:
1. Generate a null hypothesis, its corresponding alternate hypothesis, and the significance level.
2. Identify a statistical analysis to assess the truth of the null hypothesis.
3. Compute the p-value using statistical analysis.
4. Compare p-value to the significance level.
5. Reject (or fail to reject) the null hypothesis and generate the conclusion.

### Implement and evaluate simple linear regression and multiple linear regression models for a given dataset.  
**linear regression** is a statistical model that is used to predict a continuous dependent variable based on one or more independent variables fitted to the equation of a line. The job of a linear regression analysis is to calculate the slope and y intercept values (also known as coefficients) that minimize the overall distance between each data point from the linear model. There are two basic types of linear regression:
- **Simple linear regression** builds a linear regression model with one independent variable.

- **Multiple linear regression** builds a linear regression model with two or more independent variables. 

### Implement and evaluate the one-sample t-Tests, two-sample t-Tests, and analysis of variance (ANOVA) models for a given dataset.  
There are two main forms of the t-test that we use: the one-sample t-test and the two-sample t-test. 
- The **one-sample t-test** is used to assert if there is a statistical difference between the means of a sample dataset and hypothesized, potential population dataset.  

- The **two-sample t-test** determines whether the means of two samples are statistically different.

- A **pair t-test** is when we pair observations in one dataset with observations in another.  

- the **analysis of variance (ANOVA) test** compares the means across more than two samples or groups.  

### Implement and evaluate a chi-squared test for a given dataset.  
The **chi-squared test** is used to compare the distribution of frequencies across two groups and tests the following hypotheses:
- H0 : There is no difference in frequency distribution between both groups.

- Ha : There is a difference in frequency distribution between both groups.  

Before we can perform our chi-squared analysis, we must ensure that our dataset meets the assumptions of the statistical test:
1. Each subject within a group contributes to only one frequency. In other words, the sum of all frequencies equals the total number of subjects in a dataset.
2. Each unique value has an equal probability of being observed.
3. There is a minimum of five observed instances for every unique value for a 2x2 chi-squared table.
4. For a larger chi-squared table, there is at least one observation for every unique value and at least 80% of all unique values have five or more observations.  

### Identify key characteristics of A/B and A/A testing.  
**A/B testing** is a randomized controlled experiment that uses a control (unchanged) and experimental (changed) group to test potential changes using a success metric. A/B testing is used to test whether or not the distribution of the success metric increases in the experiment group instead of the control group.  

### Determine the most appropriate statistical test for a given hypothesis and dataset.
We can apply the following logic to determine the most appropriate statistical test: 
- If the success metric is numerical and the sample size is small, a z-score summary statistic can be sufficient to compare the mean and variability of both groups.

- If the success metric is numerical and the sample size is large, a two-sample t-test should be used to compare the distribution of both groups.

- If the success metric is categorical, you may use a chi-squared test to compare the distribution of categorical values between both groups.   

## Challenge Overview  
In this challenge, we performed a series of statistical tests and created a technical report that provides our interpretation of the findings.  

[MechaCarWriteUp.txt](/MechaCarWriteUp.md)  
[MechaCarChallenge.R](MechaCarChallenge.R)

## Challenge Objectives  
- Design and interpret a multiple linear regression analysis to identify variables of interest.
- Calculate summary statistics for quantitative variables.
- Perform a t-test in R and provide interpretation of results.
- Design your own statistical study to compare vehicle performance of two vehicles.  

## Challenge Summary  
[MechaCar Technical Report](/MechaCarWriteUp.md)

**AutosRUs’ newest prototype, the MechaCar, is suffering from production troubles. There are a number of issues surrounding the vehicle’s specifications and manufacturing process that are blocking the manufacturing team from proceeding. We performed a series of statistical tests on the production data in order to justify some last-minute design decision.**

We combined our understanding of R and statistics with the manufacturing datasets provided:  

- [MechaCar_mpg.csv]()- The results of an mpg testing dataset of 50 potential prototype MechaCars. The MechaCar prototypes were produced using multiple design specifications to identify ideal vehicle performance. Multiple metrics such as vehicle length, vehicle weight, spoiler angle, drivetrain, and ground clearance were collected for each vehicle.  

- [Suspension_coil.csv]()- MechaCar suspension coil test results from multiple production lots. In this dataset, the weight capacity of multiple suspension coils were tested to determine if the manufacturing process is consistent across lots. 

We generated a robust technical report that can be used to justify design choices using quantitative and qualitative reasoning.  

### MPG Regression
**We used multiple linear regression to design a linear model that predicts the mpg of MechaCar prototypes using a number of variables within the MechaCar mpg dataset.**  

Variables/coefficients that provided a non-random amount of variance to the mpg values in the dataset:
- Vehicle Length
- Vehicle Height
- Spoiler Angle
- Ground Clearance   

<img align="left" width="250" src="/pics/mpg_vl_plot.png"><br/>  
<img align="left" width="250" src="/pics/mpg_vw_plot.png"><br/>  
<img align="left" width="250" src="/pics/mpg_sa_plot.png"><br/>  
<br/>
<br/>
<br/>
<br/>  
<img align="left" width="250" src="/pics/mpg_gc_plot.png"><br/>  
<img align="left" width="250" src="/pics/mpg_awd_plot.png"><br/>  
<br/>
<br/>
<br/>
<br/>
<br/>  

**AWD** has no significant linear relationship, the dependent value is determined by random chance and error. Therefore, the linear model is a flat line with a slope of 0.  

Using our visualization in combination with our calculated p-value and r-squared value, we have determined that there is a significant relationship between **mpg** and **vehicle_length**, as well as, **mpg** and **ground_clearance.**  

This linear model does **not** predict mpg of MechaCar prototypes effectively. After reviewing our findings, we could be more effective by not including non-substancial metrics in our statistical test.  
  
## Suspension Coil Summary
**In our RScript file, we created a summary statistics table for the suspension coil’s pounds-per-inch continuous variable, including the following metrics:** 
  - Mean
  - Median
  - Variance
  - Standard deviation  
  
  ![](/pics/coil_summary_table.png)  
  
  The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per inch. Our **coil_summary_table** shows that the current manufacturing data meets this design specification with a variance of 62.29356. 
  
## Suspension Coil T-Test
Using the same suspension coil data and the MechaCarChallenge.RScript file, We determined that the suspension coil’s pound-per-inch results are **not** statistically different from the mean population results of 1,500 pounds per inch. 

<img align="left" width="400" src="/pics/PSI_population_table.png"><br/>  
<img align="left" width="400" src="/pics/PSI_sample_table.png"><br/>
<br/>
<br/>
<br/>
<br/>  
<br/>
<br/>
<br/>  
<br/>
<br/>  

## Design Our Own Study
**We designed a study that compares the performance of the MechaCar prototype vehicle to other comparable vehicles on the market. A statistical study that can quantify how the MechaCar outperforms the competition. In our study design, we considered the following:**  

- Metrics that would be of interest to a consumer
- Determine what question we would ask, what the null and alternative hypothesis would be to answer that question, and what statistical test could be used to test this hypothesis.
- Knowing what test should be used, what data should be collected?  
 
Many companies are capturing and analyzing data to increase thier opportunity for growth. Customer satisfaction surveys, units sold, service repair information, and a variety of many other metrics are typically obtained. Collecting this data is excellent and leads to the ability to make more informed decisions. However, when using data to make informed decisions in a professional environment, implementing a statistics function is not the biggest challenge. Rather, it’s determining what questions to ask.  

### What metrics would be of interest to a consumer (cost, fuel efficiency, color options, etc.)?  
There are tons, but we are going to narrow it down to three that MechaCar would benefit from taking a look at.  
- Color  
- In-Car Technology  
- Cost  

**Color**  
We chose color as the top metric that would be of interest to a consumer because that is the first thing people see about any car. If the color is attractive, then we have their attention to show them how the performance of the MechaCar prototype vehicle is to comparable vehicles on the market.  

To verify the top selling color cars, we would need to test our question with a regression model. To use a multiple linear regression model, we would need to collect numerical variables, such as number of units sold by color and time. Then, we can estimate a sample size by years. We can collect the data that has been curated from other dealerships from previous years. Although, color seems like a bar plot would be appropriate. Bar plots are used to visualize categorical data and can be used to represent the frequency of each categorical value in a list of categorical data. Using a multiple linear regression model will allow us to see trends. Such as, although color A was the third best selling vehicle in 2019, we can see that it has been on a downward trend since 2015. That color B will be a better choice because it is showing that sales are expected to increase and surpass those of color A in 2020.  

**In-Car Technology**  
[The 2017 AutoTrader Car Impact Tech Study](http://press.autotrader.com/research-and-data), sponsored by Cox Automotive helps dealers understand which technology features consumers want in their cars. One of the most insightful statistics from the study was the amount of money car buyers are willing to pay for the technology features they want. Consumers will spend an average of $2,276 to have their preferred tech capabilities. Because of the awesome insight this study brought us in 2017 and how rapid technology grows, we wanted more relevent numbers going into 2020.  

To verify the top selling in-car technology, we would want to use a more advanced visualization. The boxplot is used to visualize a variety of summary statistics for a continuous numerical vector. Boxplots are very common in data science due to the density of information contained within a single visualization, as well as the boxplot’s ability to compare measurements across grouping factors. To generate a boxplot in ggplot2, we must supply numeric vector assigned to the y-value. This is due to the ggplot accounting for multiple boxplots in a single figure. If we were to supply all the in-car technology options as our categorical grouping factor to x, we can create a boxplot that compares measurements from a variety of groups. The grouped boxplots would be easy to read and interpret to answer what in-car technology consumers have purchased. As to include those features in our MechaCar.  

**Cost**  
Consumer want to feel like they got a deal. Cost is our last metric to study. MechaCar would have to have a completed vehicle to compare to other "comparable" vehicles. Both vehicles would have to be as close in all specs in order to have accurrate and meaningful results. Due to this high importantce, a few test would need to be done. The order of execution is imperative. 

- The two sample test  
- pair t-test  
- Heatmap
  
The two-sample t-test will be used to compare two samples from a single population dataset. We would perform a two-sample t-test on each assumed comparable vehicle. Data that seems reliable from these results will provide us with the list of vehicles to continue with a pair t-test, because we would pair observations in one dataset with observations in another.  

We would use the pair t-test to compare cost of a MechaCar across the list of comparable vehicles. If the difference between our paired observations (the true mean difference, or “μd”) is equal to zero, then that comparable vehicle will go on into our heatmap plot.  

Heatmap plots help visualize the relationship between one continuous numerical variable and two other variables (categorical or numerical). Heatmaps display numerical values as colors on a two-dimensional grid so that value clusters and trends are readily identifiable. We can visualize the average cost of comparable vehicles across the type of vehicle class from 2010 to 2020.

## Limitations  
R and most of R’s libraries are licensed as General Public License, version 2 (GPL 2). This means that if you program or model anything using R, GPL forces your application, program, or script to be open source.
