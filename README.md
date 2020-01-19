# Goddard_Shannon_R-Analysis

In this challenge, you’ll perform a series of statistical tests and create a technical report that provides your interpretation of the findings.  

#### Background
From the upper management team, Jeremy received two datasets:
- The results of an mpg testing dataset of 50 potential prototype MechaCars. The MechaCar prototypes were produced using multiple design specifications to identify ideal vehicle performance. Multiple metrics such as vehicle length, vehicle weight, spoiler angle, drivetrain, and ground clearance were collected for each vehicle.
- MechaCar suspension coil test results from multiple production lots. In this dataset, the weight capacity of multiple suspension coils were tested to determine if the manufacturing process is consistent across lots.  

By combining his understanding of R and statistics with the manufacturing datasets provided by the upper management, Jeremy should have all the materials he needs to generate a robust technical report. Technical reports such as the one Jeremy will design are common in product development and are used to justify design choices using quantitative and qualitative reasoning.  

## Objectives
The goals of this challenge are for you to complete the following:
- Design and interpret a multiple linear regression analysis to identify variables of interest.
- Calculate summary statistics for quantitative variables.
- Perform a t-test in R and provide interpretation of results.
- Design your own statistical study to compare vehicle performance of two vehicles.
#### Instructions
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

### Design Your Own Study
Upper management is looking for your expertise and wants you to design a study that compares the performance of the MechaCar prototype vehicle to other comparable vehicles on the market. In the MechaCarWriteUp.txt text file, write a short description of a statistical study that can quantify how the MechaCar outperforms the competition. In your study design, be sure to write about the following considerations:
- Think critically about what metrics you would think would be of interest to a consumer (cost, fuel efficiency, color options, etc.).
- Determine what question we would ask, what the null and alternative hypothesis would be to answer that question, and what statistical test could be used to test this hypothesis.
- Knowing what test should be used, what data should be collected? Hint: Look at the cheat sheet for required variables.  

## Submission
Make sure your repo is up to date and includes the following:
- A MechaCarChallenge.RScript file containing all of your R code for the technical report
- A MechaCarWriteUp.txt text file, containing your interpretation and findings for each statistical analysis.
Submit a link to your repository through Canvas.
