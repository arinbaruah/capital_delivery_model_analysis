


# Enhancing Future Capital Delivery: A Comparative analysis of Melbourne Water Corporation’s Project Models

> [!NOTE]
> The final deliverables for this project have been successfully completed and are outlined below.

# Repository Navigation
```
.
├─── final_report                      # Presentation files
│    └──  Final_report.qmd             # Markdown version of final report
│    └──  Final_report.pdf             # PDF version of final report
├──  data_dictionary.md                # Markdown version of the data dictionary
├─── presentation                      # Presentation files
│    └──  Final_presentation.pptx      # Final presentation PPT
│    └──  Interim_presentation.pptx    # Interim presentation PPT
├──  images                            # Important images for report
├──  literature                        # Folder containing references to literature
├─── data                              # Datasets
│    └── Capital_Delivery_Project_deidentified.csv  # De-identified project data
│                                
└── ...
```
# Reproduce this analysis

Steps to reproduce the analysis are as follows:

1. [Download and install R and R Studio](https://posit.co/download/rstudio-desktop/)
2. Open a new project in R Studio and select
    - "Version Control" -> "Git"
    - Enter repository URL as https://github.com/arinbaruah/capital_delivery_model_analysis.git
4. After opening the R project, run the command `renv::activate` in the __R console__.
5. After the R project has been activated, run the command `renv::restore` in the __R console__ to obtain the appropriate package versions for reproducing the analysis.
6. Once all the packages are updated/restored, run the following command in __R terminal__ to render the PDF file

```
quarto render final_report/Final_report.qmd
```
7. The output PDF file can now be found in the `final_report` folder as a file named `Final_report.pdf`
   
# Acknowledgement

![](https://github.com/arinbaruah/capital_delivery_model_analysis/blob/main/images/org_logo.png)

The ongoing project aimed at optimizing the infrastructure capital delivery model through exploratory data analysis and implementing forecasting techniques draws guidance from the Department of Econometrics and Business Statistics, Monash University and Major Capital Delivery, Melbourne Water Corporation. This partnership leverages Monash University’s expertise in data analysis and forecasting with Melbourne Water Corporation’s extensive infrastructure knowledge to enhance project delivery efficiency and accuracy.

# Quick links to project files

1. [Final executive report](https://github.com/arinbaruah/capital_delivery_model_analysis/blob/main/final_report/Final_report.pdf) [Finalised] 🎬
2. [Final presentation](https://github.com/arinbaruah/capital_delivery_model_analysis/blob/main/presentation/Final_presentation.pptx) [Finalised] 🎬
3. [Data dictionary](https://github.com/arinbaruah/capital_delivery_model_analysis/blob/main/data_dictionary/data_dictionary.md) 📕🧑‍🏫

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
| `PBC`                    | Datetime            | A date on which the first business case is submitted
| `BCA`                    | Datetime            | A date on which the business case is approved and the project |
| `Stage1`                 | Datetime            | A date on which the first stage of practical completion of project is reached |
| `Stage2`                 | Datetime            | A date on which the second stage of practical completion of project is reached |
| `Stage3`                 | Datetime            | A date on which the defect detection period of project is reached |
| `EPT`                    | Character           | An indicator for the number of gates (approvals) a project must go through |
| `Owner Team`             | Character           | The subdivision within Melbourne Water Corporation responsible for completing the project |

# Background 🕵🏻‍♀️

The Capital Delivery Model is crucial for optimising project management within the water industry. It provides a structured approach to engaging project personnel and service providers, ensuring efficient project execution and successful timely outcomes. However, designing and reviewing such a model presents significant challenges, including managing external partnerships along with their risks, rising project costs, and securing approvals from higher authorities for timely approvals.


# Objective 🎯

This study aims to create a reproducible framework for analysing project data across various delivery models to establish a benchmark for designing a new model. By conducting focused exploratory and temporal data analysis on historical project data and standardising results, the study seeks to set preliminary expectations for the future of capital delivery. It will additionally implement benchmark and specialised time series forecasting techniques, the ETS model, by decomposing the time series into trend, seasonality, and residuals. The model will continuously learn and improve with new data, extending its usefulness beyond the next pricing submission period.
 
The major areas of study for the current analysis are delineated as follows:

1. __Distribution of Projects by Delivery Model:__ Examination of current and past projects categorised by delivery model, based on the overall cost of the project.
2. __Implication of the distribution of projects on overall project valuations:__ Analysis of the number of projects associated with each delivery model along with their subsequent cost valuations, thereby providing a range of potential outcomes and expectations for the new delivery model.
3. __Project Duration Analysis:__ Investigation of project durations relative to their overall valuations.
4. __Approval Duration Distribution:__ Assessment of the time required for project approvals across different stages.
5. __Future Project Forecast:__ Estimation of the number of projects anticipated in the delivery period from 2026 to 2031.
6. __Tracking service provider’s performance through KRAs and KPIs:__ Adoption of a fair and transparent assessment tracking methodology to incentivise the service provider for taking timely, inclusive, sustainable and safe initiatives.

# Key insights 🧐

The systematic approach to studying the historical capital delivery models and projecting insights into the future delivery model yielded the following key outcomes:

1. Based on the analysis of sample data from CDM-21 and CDM-16, the new delivery model is projected to successfully deliver __at least 70% of the projects with a forecasted final cost (FFC) of $5 million or less.__

![](https://github.com/arinbaruah/capital_delivery_model_analysis/blob/main/images/distribution_cost_bands.jpeg)

2. Comparison of the duration of business case submission between CDM-16 and CDM-21 for Major Framework A indicated an increase in average submission duration. To check if the increase was statistically significant, a non-parametric 1 sided permutation test was performed. Based on the results, with 95 % confidence, it can be said that the average duration in CDM-21 is significantly higher than average duration in CDM-16. This means it is taking significantly longer in the current model to submit business cases when compared to the previous model.

![](https://github.com/arinbaruah/capital_delivery_model_analysis/blob/main/images/permutation_test_framework.jpeg)
   

3. Projects with higher valuations and associated risks require approval from higher authorities, often external to the department or organization. This can lead to significantly longer approval times, with some projects taking well over a year to reach the “approved” stage. The current study recommends segmenting high-valuation projects into smaller, “bundled” projects to expedite the approval process, __potentially reducing the approval duration to approximately 8 months (250 days) and follow an approval process which is within the department or the organisation.__

![](https://github.com/arinbaruah/capital_delivery_model_analysis/blob/main/images/approval_duration_distribution.jpeg)   

4. In the upcoming delivery model, it is expected that __more than half of all the projects will need to be approved by the "Level 3 authority".__ Additionally, the percentage of projects approved by the “Level 2 authority”, “Finance and Audit” and “Managing Director (MD)” has remained __consistent over the past two CDMs,suggesting a stable pattern in the composition of future approvals.__

![](https://github.com/arinbaruah/capital_delivery_model_analysis/blob/main/images/approval_bodies_duration.jpeg)

5. An ETS forecast model was trained on historical data to predict the expected number of projects valued at ≤ $5 million. The forecasts indicate an average of approximately three projects per month, with a notable annual peak observed mid-year and another towards the year’s end.

![](https://github.com/arinbaruah/capital_delivery_model_analysis/blob/main/images/ets_ana_model_forecast_results.jpeg)

6. Although __Minor Framework A delivery program projects account for approximately 10 % of the total valuation of projects__ within a CDM, the labour utilisation is however the same as that of Frameworks delivery program projects which delivers a significantly larger proportion of the total valuation. The future Capital Delivery Model for PS-26 should explore __streamlining or bundling multiple Minor Framework A projects to enhance efficiency in project management and optimize labor resource allocation.__

![](https://github.com/arinbaruah/capital_delivery_model_analysis/blob/main/images/labour_hours.png)

7. A scoring system mechanism was implemented through the KRA-KPI metric dashboards and templates, allowing Melbourne Water to __perform fair and transparent assessments of a service provider's project initiatives__, and at the same time, __financially incentivise them to improve over the course of the project__.

![](https://github.com/arinbaruah/capital_delivery_model_analysis/blob/main/images/dashboard.png)
![](https://github.com/arinbaruah/capital_delivery_model_analysis/blob/main/images/payout.png)

