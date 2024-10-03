


# Enhancing Future Capital Delivery: A Comparative analysis of Melbourne Water Corporation’s Project Models

> [!WARNING]
> The project is currently under progress and will be notified on this space once project deliverables are ready

# Repository Navigation
```
.
├── cdmr_report_monash.qmd  # Reproducible analysis file in .qmd format
├── cdmr_report_monash.pdf  # Rendered project report in PDF format
├── Short_talk.pptx         # Interim 3-minute presentation
├── Final_presentation.pptx # Final 10-minute presentation
├── images                  # Important images for report
├── literature              # Folder containing references to literature
├─── data                   # Datasets
│   └── Capital_Deliver_Project_deidentified.csv  # De-identified project data
│                                
│                                    
└── ...
```
# Reproduce this analysis

Steps to reproduce the analysis are as follows:

1. [Download and install R and R Studio](https://posit.co/download/rstudio-desktop/)
2. Open a new project in R Studio and select
    - "Version Control" -> "Git"
    - Enter repository URL as https://github.com/arinbaruah/capital_delivery_model_analysis.git
4. After opening the R project, run the command `renv::restore` in the __R console__.
5. Once all the packages are updated/restored, run the following command in __R terminal__ to render the PDF file

```
quarto render cdmr_report_monash.qmd
```

# Acknowledgement

![](https://github.com/arinbaruah/capital_delivery_model_analysis/blob/main/org_logo.png)

The ongoing project aimed at optimizing the infrastructure capital delivery model through exploratory data analysis and implementing forecasting techniques draws guidance from the department of Business and Econometrics, Monash University and Major Capital Delivery, Melbourne Water Corporation. This partnership leverages Monash University’s expertise in data analysis and forecasting with Melbourne Water Corporation’s extensive infrastructure and inknowledge to enhance project delivery efficiency and accuracy.

# Quick links to project files

1. [Final executive report](https://github.com/arinbaruah/capital_delivery_model_analysis/blob/main/cdmr_report_monash.pdf) [Under progress] 🚧
2. [Final presentation](https://github.com/arinbaruah/capital_delivery_model_analysis/blob/main/CDMR_analysis.html) [Under progress] 🏗️
3. [Data dictionary](https://github.com/arinbaruah/capital_delivery_model_analysis/blob/main/data_dictionary.md)

# License

![](https://github.com/arinbaruah/capital_delivery_model_analysis/blob/main/images/cc_license.jpeg)

This repository is licensed under Creative Commons Legal Code CC0 1.0 Universal and can be referred to [here](https://github.com/arinbaruah/capital_delivery_model_analysis/blob/main/LICENSE).

# About the data


| Variable name            | Class               | Description
| ---------------          | ---------------     | -------------- |
| `ID`                     | Character           | Unique identification for each individual project |
| `FFC`                    | Double              | An estimate of the total valuation of the project in dollar value |
| `Delivery Program`       | Character           | The classification of the project based on the capital delivery program framework |
| `Tender Closed`          | Datetime            | A date on which the tender process (if applicable) for the project was closed |
| `Owner Group`            | Character           | The division within Melbourne Water Corporation responsible for completing the particular project |
| `BNI`                    | Datetime            | Business Need Identifier is a date on which a project concept is first conceived  |
|`PBC`                     | Datetime            | A date on which the first business case is submitted
| `BCA`                    | Datetime            | A date on which the business case is approved and the project |
| `Stage1`                 | Datetime            | A date on which the first stage of practical completion of project is reached |
| `Stage2`                 | Datetime            | A date on which the second stage of practical completion of project is reached |
| `Stage3`                 | Datetime            | A date on which the defect detection period of project is reached |
| `EPT`                    | Character           |An indicator for the number of gates (approvals) a project must go through |
| `Owner Team`             | Character           |The subdivision within Melbourne Water Corporation responsible for completing the project |

# Background 🕵🏻‍♀️

The Capital Delivery Model is crucial for optimizing project management within the water industry. It provides a structured approach to engaging project personnel and service providers, ensuring efficient project execution and successful timely outcomes. However, designing and reviewing such a model presents significant challenges, including managing external partnerships along with their risks, rising project costs, and securing approvals from higher authorities for timely approvals.


# Objective 🎯

This study aims to create a reproducible framework for analysing project data across various delivery models to establish a benchmark for designing a new model. By conducting focused exploratory and temporal data analysis on historical project data and standardising results, the study seeks to set preliminary expectations for the future of capital delivery. It will additionally implement benchmark and specialised time series forecasting techniques, including ETS and SARIMA, by decomposing the time series into trend, seasonality, and residuals. The model will continuously learn and improve with new data, extending its usefulness beyond the next pricing submission period.
 
The major areas of study for the current analysis are delineated as follows:

1. __Distribution of Projects by Delivery Model:__ Examination of current and past projects categorised by delivery model, based on the overall cost of the project.
2. __Implication of the distribution of projects on overall project valuations:__ Analysis of the number of projects associated with each delivery model along with their subsequent cost valuations, thereby providing a range of potential outcomes and expectations for the new delivery model.
3. __Project Duration Analysis:__ Investigation of project durations relative to their overall valuations.
4. __Approval Duration Distribution:__ Assessment of the time required for project approvals across different stages.
5. __Future Project Forecast:__ Estimation of the number of projects anticipated in the delivery period from 2026 to 2031.
6. __Tracking service provider’s performance through KRAs and KPIs:__ Adoption of a fair and transparent assessment tracking methodology to incentivise the service provider for taking timely, inclusive, sustainable and safe initiatives.

# Key insights 🧐

The systematic approach to studying the historical capital delivery models and projecting insights into the future delivery model yielded the following key outcomes:
 
1. The entire analysis was conducted in R, providing the key benefit of a formalised, automated and reproducible pipeline for data handling and cleaning based on critical assumptions. This code is scalable for future purposes and is expected to significantly reduce data cleaning duration by at least 30 %, making it suitable for processing live project data in the future.
2. Based on historical data analysis of past delivery models, it is anticipated that over 70% of the upcoming projects will be valued at $5 million or less. Given the high volume of projects in this category, it is likely that a specialised project approval process would positively affect the efficient and timely delivery of these projects. Additionally, a dedicated team may be established to efficiently manage and deliver these projects for its efficient delivery.
3. Further analysis reveals that projects valued at $5 million or less, which constitute nearly 70% of the projects within a capital delivery model, account for only 10% of the total project costs. This suggests that, despite requiring similar manpower resources as larger projects, these smaller projects contribute only a fraction of the overall project valuation, further highlighting the need for a dedicated team to effectively manage and execute these projects.
4. Analysing the historical breakdown of projects based on the approving body has provided valuable insights into how future model distributions might look. Specifically, the duration of project approval varies depending on the approving authority. By examining approval durations, we can establish benchmarks for the approval process timeline. This information is crucial for effective planning and for proactively addressing potential risks related to approval delays.
5. Analysing the duration of critical stages in the project lifecycle, based on delivery programs and project valuations, has revealed that some projects, on average, take longer to complete than others. This analysis provides valuable benchmarks and insights, allowing us to monitor current projects against historical expectations and identify any deviations early on. 
6. A key focus of this study is to accurately predict the number of projects expected each year and month in the next delivery model. By employing classical additive time series decomposition, we can analyse the project data to uncover important characteristics such as trends, seasonality, and residuals. Building on these insights, we use specialized forecasting methods, specifically the Error-Trend-Seasonality (ETS) and  Seasonal-ARIMA models, to predict future project volumes. These models offer the advantage of continuous learning, allowing them to adapt and remain applicable beyond the next delivery model as more data becomes available. Based on the results obtained, it could be observed that the forecasting model predicted on average, 3 new approved projects in each month with 2 peaks in a year, one during the mid year while one at the end of the year. These peaks indicate a higher than average number of approved projects. This forecasting is potentially crucial for efficient crew resource management during project execution. 


