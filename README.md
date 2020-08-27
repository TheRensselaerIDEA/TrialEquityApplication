# TrialEquity Application

[![License](https://img.shields.io/badge/License-Apache2-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0) 

[**TrialEquity**]( https://miao-qi-rpi-app.shinyapps.io/TrialEquity/)is an interactive web-based R-Shiny app founded upon our novel randomized clinical trial (RCT) inequity metrics derived from machine learning fairness measures. It is designed to quantify and visualize the inequities in clinical trials and provide insights to improve the clinical trial equity and health equity, with specific considerations for diverse user groups including clinicians, researchers, and health policy advocates. 


<!-- TABLE OF CONTENTS -->
## Contents

1. [Project Description](#project-description)
1. [Application Features](#application-features)
1. [Example](#example)
1. [Contact](#contact)
1. [License](#license)
1. [Acknowledgments](#acknowledgments)


<!-- ABOUT THE PROJECT -->
## Project Description
We develop randomized clinical trial (RCT) inequity metrics based on Machine Learning (ML) Fairness Research. Visualizations and statistical tests based on proposed metrics enable researchers and physicians to rapidly visualize and assess potential inequities in RCTs for subgroups. The approach enables users to determine overrepresentation, underrepresentation, and exclusion of subgroups indicating potential limitations of RCTs. The method could help support evaluation of existing RCTs, design of new RCTs, monitoring of RCT recruitment, and applicability of RCT results to patients.

### What's the problem?
Within the field of RCT research, there has been ongoing concern that RCTs which lack a diversity of participants may not provide clear evidence of efficacy and safety for new interventions in underrepresented or missing subpopulations. To date, there has been no efficient means to quantify the inequity between those who get enrolled into RCTs and the broader population who could benefit from the new intervention.


### How can technology help?
Extensive  research  in  ML fairness  has  created  metrics  for  quantifying  inequities  in  trained  ML classification models and for creating novel ML approaches to address these inequities.

Our novel insight is that assignment of a subject to a RCT can be regarded as a classification function that is random. Applying ML-fairness metrics to this classification problem creates novel inequity metrics for RCTs and other clinical studies. The inequity metrics capture how well the actual assignment of subjects to a RCT matches of a hypothetical random assignment.


### The solution
We compare the observed rate in the RCT for the subgroup to the hypothetical ideal rate in an equitable RCT in which patients are assigned truly randomly to the clinical trial.  By considering assignment to the clinical trial as a random classification function, we develop standardized metrics based on variations of ML fairness metrics, focusing here on "Disparate Impact." The resulting metrics are functions of disease-specific observed and ideal rates of assignment of protected subgroups to the RCT. 

## Application Features

You can run the example studies on [**TrialEquity**]( https://miao-qi-rpi-app.shinyapps.io/TrialEquity/).

The tool can
1. Measure inequity in randomized clinical trials
2. Visualize inequity for subgroups
3. Compare inequities among studies

The R codes are available in the folder **Codes**.

### Prerequisites

What things you need to install the software and how to install them:
1. A software/server that can run R shiny codes
2. R packages used in the codes (available in *Source.R*)


## Example
We apply the proposed RCT equity metrics to three landmark clinical trials released in the last decade: Action to ControlCardiovascular Risk in Diabetes (**ACCORD**), Antihypertensive and Lipid-Lowering Treatment to Prevent Heart AttackTrial(**ALLHAT**), and Systolic Blood Pressure Intervention Trial (**SPRINT**). All patient data are obtained through the [BiologicSpecimen and Data Repositories Information Coordinating Center (BioLINCC)](https://biolincc.nhlbi.nih.gov/home/).





<!-- CONTACT -->
## Contact

Miao Qi  - qim@rpi.edu

Project Link: [ClinicalTrialEquity](https://github.com/TheRensselaerIDEA/TrialEquityApplication)

## License

This project is licensed under the Apache 2 License

## Acknowledgments

* This work was primarily funded by IBM Research AI Horizons Network with the Rensselaer Institute for Data Exploration and Applications (IDEA)
