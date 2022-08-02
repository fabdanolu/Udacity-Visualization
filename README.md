# Analysis of Loan Data From Prosper
## by Fabi Daniel


<ul>
<li><a href="#intro">Introduction</a></li>
<li><a href="#overview">Project Overview</a></li>
<li><a href="#conclusions">Summary of Findings</a></li>
<li><a href="#ll">Limitations and Learning Curve</a></li>
</ul>

<a id='intro'></a>
#### Introduction
This repository contains the project files both html and ipynb, the dataset in csv and the readme in md. 
The Packages used on this project include 
* Numpy Version '1.23.1' - For arrays
* Pandas Version '1.4.3' - For 2D Data Structure 
* Matplotlib Version 3.5.2 - For Visualization
* Seaborn Version '0.11.2' - For Visualization 

<a id='overview'></a>
#### Project Overview

> This data set contains 113,937 loans with 81 variables on each loan, including loan amount, borrower rate (or interest rate), current loan status, term, borrower income, and many others. The dataset was later trimmed to 12 columns removing columns that are surplus to our investigation and deleting rows with Null Values.
Special Focus was put on some variables based on the assumption that the **Rates**, **Principal** and **Term** are important in any loan Situation.

<a id='conclusions'></a>
#### Summary of Findings

##### Univariate Exploration

I discover that there are similarities in BorrowerAPR and BorrowerRate Charts. This relationship was further explored in the BiVariate Exploration part of this project. There was no need to make any transformation on the two variables. 
Majority of the Loans are either completed or currently running. LoanOriginalAmount has a rightly Skewed distribution which majority of the loan amount are Closer to the Lower limit. **Employment Status** is ***not*** a factor that affects **Loan Status** as 90%+ of the population are employed. I wanted to find out one thing, whether borrowers were `employed or not`. This not a variable of interest. I had to make transformation to the EmploymentStatus variable. I wanted to know the ratio of employed borrowers to that of the unemployed. I was able group the values into two distinct categories. It's either you are employed or not, irrespective of the type and nature of your employment. 
Homeowners was evenly distributed between `True` | `False`, with true edging it out.  This is also not a variable of interest and further investigation was not done on it. Majority of loans were `36` Months while `12` months loan were hardly subscribed to.  Just like LoanOriginalAmount, MonthlyPaymenthas has a rightly skewed


##### BiVariate Exploration

I dug deeper to understand the similarities that I Observed in the Univariate Visualizations of two variables 'BorrowerRate' & 'BorrowerAPR'. Using a scatterplot, I was able to establish that there is a positive linear relationship between these two variables. So I endeavour to use them interchangeably throughout the project.
Interestingly, LoanOriginalAmount has a Negative Correlation with Rates(BorrrowerRate and BorrowerAPR).  
    * It seems some borrowers with higher loan amount get lower rates compared to others. The decrease/increase in loan amount doesnt have a direct relationship with the Rates
    * Next Step would be to investigate further into the phenomenon

LoanOriginalAmount has a Positive Correlation with MonthlyLoanPayment. This is expected. I discovered that Past Due(>120 days) has the highest minimum rate, while the lowest minimum is in the Positive Loan Status i.e. Completed Status followed by the current status.
Also, Prosper Rating C & B are the most subscribed, Rating D is the most completed, area of further investigation could include the ratio of each loan status for Prosper Rating.


##### MultiVariate Exploration

Across all loan terms, ***Positive Loan Status*** have lower rates especially for the 12 months loan. For example, 12 months loans with ***Negative Loan Status*** have rates higher than `15%` while the reverse is the case for the ***Positive Loan Status***. This is predominant for other loan terms
I can assume that lower BorrowerRate is a factor of ***Positive Loan Status***. As earlier established, *Current* and *Completed* **respectively** are still the most occuring **Loan Status** even across all prosper ratings. However, Even though there are few counts, *12 months* loans have more completed than they have currently running. Prosper Rating C represents the majority, Rating D has the best completion ratio.



##### Key Insights for Presentation

> The investigation showed that LoanStatus, Current and Completed that are elements in my assumed **Positive Loan Status** are the most occuring and also have the lowest Rates. BorrowerRate and BorrowerAPR have a positive correlation
Across all terms the Frequency and Order of the Loan Status have always been consistent with only the exception of 12 months loans, having more completed than current.

<a id='ll'></a>
#### Limitations & Learning Curve

* Supplemented statistics with visualizations to build understanding of data.
* Created appropriate plots, limits, transformations, and aesthetics to explore a dataset to understand distributions of variables and relationships between features.
* Used design principles to create effective visualizations for communicating findings to an audience.
