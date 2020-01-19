![Header](/pics/header.png)

#### Table of Contents

[Project Overview](#project-overview)  
[Resources](#resources)  
[Objectives](#objectives)  
[Summary](#summary)  

- [Load, clean up, and reshape datasets using tidyverse in R.](#Load-clean-up-and-reshape-datasets-using-tidyverse-in-R)  
- [Visualize datasets with basic plots such as line, bar, and scatter plots using ggplot2.](#Visualize-datasets-with-basic-plots-such-as-line-bar-and-scatter-plots-using-ggplot2)  
- [Generate and interpret more complex plots such as boxplots and heatmaps using ggplot2.](#Generate-and-interpret-more-complex-plots-such-as-boxplots-and-heatmaps-using-ggplot2)  
- [Plot and identify distribution characteristics of a given dataset.](#Plot-and-identify-distribution-characteristics-of-a-given-dataset)  
- [Formulate null and alternative hypothesis tests for a given data problem.](#Formulate-null-and-alternative-hypothesis-tests-for-a-given-data-problem)  
- [Implement and evaluate simple linear regression and multiple linear regression models for a given dataset.](#Implement-and-evaluate-simple-linear-regression-and-multiple-linear-regression-models-for-a-given-dataset)  
- [Implement and evaluate the one-sample t-Tests, two-sample t-Tests, and analysis of variance (ANOVA) models for a given dataset.](#Implement-and-evaluate-the-one-sample-t-Tests-two-sample-t-Tests-and-analysis-of-variance-ANOVA-models-for-a-given-dataset)  
- [Implement and evaluate a chi-squared test for a given dataset.](#Implement-and-evaluate-a-chi-squared-test-for-a-given-dataset)  
- [Identify key characteristics of A/B and A/A testing.](#Identify-key-characteristics-of-AB-and-AA-testing)  
- [Determine the most appropriate statistical test for a given hypothesis and dataset.](#Determine-the-most-appropriate-statistical-test-for-a-given-hypothesis-and-dataset)  

[Challenge Overview](#challenge-overview)  
[Challenge Objectives](#challenge-objectives)  
[Challenge Summary](#challenge-summary)  

- [MPG Regression](#MPG-Regression)  
- [Suspension Coil Summary](#Suspension-Coil-Summary)  
- [Suspension Coil T-Test](#Suspension-Coil-T-Test)  
- [Design Our Own Study](#Design-Our-Own-Study)  

[Limitations](#limitations)

## Project Overview
In R-Analysis, we applied our understanding of statistics and hypothesis testing to analyze a series of datasets from the automotive industry. Our analysis includes visualizations, statistical tests, and interpretation of the results. All of our statistical analysis and visualizations are written in the R programming language.  

Throughout the module, we extract, transform, and load (ETL) data; visualize the data; and analyze the data using R. Additionally, we learned a variety of statistical tests, their real-world application in data science, and their implementation in R.  

## Resources  
- **Data Source:** [demo.csv](), [demo.json](), [demo2.csv](), [mpg_modified](), [used_car_data](), [Vehicle_Data](), [MechaCar_mpg.csv](), [Suspension_coil.csv]() 
- **Software:** RStudio

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
<br/>
<br/>  

**mutate()** transforms a data frame and include new calculated data columns.  
> demo_table <- demo_table %>% mutate(Mileage_per_Year=Total_Miles/(2020-Year),IsActive=TRUE)
<img align="left" width="500" src="/pics/mutate_function.png"><br/>  
<br/>
<br/>
<br/>
<br/>  
<br/>
<br/>
<br/>
<br/>

**group_by()** tells dplyr which factor (or list of factors in order) to group our data frame by.  
> summarize_demo <- demo_table2 %>% group_by(condition) %>% summarize(Mean_Mileage=mean(odometer))
<img align="left" width="300" src="/pics/group_by_function.png"><br/>  
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

**summarize()** creates columns in our summary data frame and will use statistics summary functions such as mean(), median(), sd(), min(), max(), and n().  
> summarize_demo <- demo_table2 %>% group_by(condition) %>% summarize(Mean_Mileage=mean(odometer),Maximum_Price=max(price),Num_Vehicles=n())
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
<br/>
<br/>
<br/>

#### Reshape
When performing more involved data analytics and visualizations, there may be situations where the shape and design of our data frame is overcomplicated or incompatible with the libraries and functions we wish to use. The tidyr library from the tidyverse has the gather() and spread() functions to help reshape our data.  
<br/>  

**gather()** changes the dataset to a long format.  
> long_table <- gather(demo_table3,key="Metric",value="Score",buying_price:popularity)
<img align="left" width="200" src="/pics/gather_function.png"><br/>  
<br/>
<br/>
<br/>
<br/>

**spread()** spreads out a variable column of multiple measurements into columns for each variable.  
> wide_table <- long_table %>% spread(key="Metric",value="Score")
<img align="left" width="500" src="/pics/spread_function.png"><br/>  
<br/>
<br/>
<br/>
<br/>  
<br/>
<br/>
<br/>
<br/> 

### Visualize datasets with basic plots such as line, bar, and scatter plots using ggplot2.  
<img align="left" width="250" src="/pics/.png"><br/>  
<img align="left" width="250" src="/pics/.png"><br/>  
<img align="left" width="250" src="/pics/.png"><br/>
<br/>
<br/>
<br/>
<br/>  

### Generate and interpret more complex plots such as boxplots and heatmaps using ggplot2.  
<img align="left" width="250" src="/pics/.png"><br/>  
<img align="left" width="250" src="/pics/.png"><br/>  
<img align="left" width="250" src="/pics/.png"><br/>
<br/>
<br/>
<br/>
<br/>  

### Plot and identify distribution characteristics of a given dataset.  
<img align="left" width="250" src="/pics/.png"><br/>  
<img align="left" width="250" src="/pics/.png"><br/>  
<img align="left" width="250" src="/pics/.png"><br/>
<br/>
<br/>
<br/>
<br/>  

### Formulate null and alternative hypothesis tests for a given data problem.  
<img align="left" width="250" src="/pics/.png"><br/>  
<img align="left" width="250" src="/pics/.png"><br/>  
<img align="left" width="250" src="/pics/.png"><br/>
<br/>
<br/>
<br/>
<br/>  

### Implement and evaluate simple linear regression and multiple linear regression models for a given dataset.  
<img align="left" width="250" src="/pics/.png"><br/>  
<img align="left" width="250" src="/pics/.png"><br/>  
<img align="left" width="250" src="/pics/.png"><br/>
<br/>
<br/>
<br/>
<br/>  

### Implement and evaluate the one-sample t-Tests, two-sample t-Tests, and analysis of variance (ANOVA) models for a given dataset.  
<img align="left" width="250" src="/pics/.png"><br/>  
<img align="left" width="250" src="/pics/.png"><br/>  
<img align="left" width="250" src="/pics/.png"><br/>
<br/>
<br/>
<br/>
<br/>  

### Implement and evaluate a chi-squared test for a given dataset.  
<img align="left" width="250" src="/pics/.png"><br/>  
<img align="left" width="250" src="/pics/.png"><br/>  
<img align="left" width="250" src="/pics/.png"><br/>
<br/>
<br/>
<br/>
<br/>  

### Identify key characteristics of A/B and A/A testing.  
<img align="left" width="250" src="/pics/.png"><br/>  
<img align="left" width="250" src="/pics/.png"><br/>  
<img align="left" width="250" src="/pics/.png"><br/>
<br/>
<br/>
<br/>
<br/>  

### Determine the most appropriate statistical test for a given hypothesis and dataset.
<img align="left" width="250" src="/pics/.png"><br/>  
<img align="left" width="250" src="/pics/.png"><br/>  
<img align="left" width="250" src="/pics/.png"><br/>
<br/>
<br/>
<br/>
<br/>  

## Challenge Overview  
In this challenge, we performed a series of statistical tests and created a technical report that provides our interpretation of the findings.

## Challenge Objectives  
- Design and interpret a multiple linear regression analysis to identify variables of interest.
- Calculate summary statistics for quantitative variables.
- Perform a t-test in R and provide interpretation of results.
- Design your own statistical study to compare vehicle performance of two vehicles.  

## Challenge Summary  
By combining our understanding of R and statistics with the manufacturing datasets provided:  

- [MechaCar_mpg.csv]()- The results of an mpg testing dataset of 50 potential prototype MechaCars. The MechaCar prototypes were produced using multiple design specifications to identify ideal vehicle performance. Multiple metrics such as vehicle length, vehicle weight, spoiler angle, drivetrain, and ground clearance were collected for each vehicle.
- [Suspension_coil.csv]()- MechaCar suspension coil test results from multiple production lots. In this dataset, the weight capacity of multiple suspension coils were tested to determine if the manufacturing process is consistent across lots. 

We generated a robust technical report that can be used to justify design choices using quantitative and qualitative reasoning.  

### MPG Regression
- Create a new RScript in your R source pane and save it to your active directory. Name this new RScript file MechaCarChallenge.RScript. (Hint: Create a new RScript by going to the File menu. Select “New File” followed by “RScript.” Or you can click the icon in the top-left corner of the RStudio window. Note that the icon looks like a white square with a plus sign in the top left corner.)
- Download the MechaCar mpg dataset and place it in your active directory for your R session.
- Using multiple linear regression, design a linear model that predicts the mpg of MechaCar prototypes using a number of variables within the MechaCar mpg dataset. Create a separate text file called MechaCarWriteUp.txt. In the text file, provide a small writeup of your interpretation of the multiple linear regression results. Be sure to include the following details: 
  - Which variables/coefficients provided a non-random amount of variance to the mpg values in the dataset?
  - Is the slope of the linear model considered to be zero? Why or why not?
  - Does this linear model predict mpg of MechaCar prototypes effectively? Why or why not?  
  
### Suspension Coil Summary
- Download the suspension coil test result dataset and place it in your active directory for your R session.
- In the same MechaCarChallenge.RScript file, create a summary statistics table for the suspension coil’s pounds-per-inch continuous variable. 
Be sure to include the following metrics: 
  - Mean
  - Median
  - Variance
  - Standard deviation  
  
Using the same MechaCarWriteUp.txt text file, provide a short write-up of your interpretation and findings for the suspension coil summary statistics. Be sure to include the following details: 
  - The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per inch. Does the current manufacturing data meet this design specification? Why or why not?  
  
### Suspension Coil T-Test
- Using the same suspension coil data and the MechaCarChallenge.RScript file, determine if the suspension coil’s pound-per-inch results are statistically different from the mean population results of 1,500 pounds per inch. (Hint: Refer to the t-test section of this module to determine which statistical test to use.)
- In the MechaCarWriteUp.txt text file, provide a small writeup of your interpretation and findings for the t-test results.  

### Design Our Own Study
Upper management is looking for your expertise and wants you to design a study that compares the performance of the MechaCar prototype vehicle to other comparable vehicles on the market. In the MechaCarWriteUp.txt text file, write a short description of a statistical study that can quantify how the MechaCar outperforms the competition. In your study design, be sure to write about the following considerations:
- Think critically about what metrics you would think would be of interest to a consumer (cost, fuel efficiency, color options, etc.).
- Determine what question we would ask, what the null and alternative hypothesis would be to answer that question, and what statistical test could be used to test this hypothesis.
- Knowing what test should be used, what data should be collected? Hint: Look at the cheat sheet for required variables.

## Limitations  
R and most of R’s libraries are licensed as General Public License, version 2 (GPL 2). This means that if you program or model anything using R, GPL forces your application, program, or script to be open source.

## Submission
Make sure your repo is up to date and includes the following:
- A MechaCarChallenge.RScript file containing all of your R code for the technical report
- A MechaCarWriteUp.txt text file, containing your interpretation and findings for each statistical analysis.
