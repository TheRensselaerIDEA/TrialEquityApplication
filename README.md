# TrialEquity Application

[![License](https://img.shields.io/badge/License-Apache2-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0) 

[**TrialEquity**]( https://miao-qi-rpi-app.shinyapps.io/TrialEquity/)is an interactive web-based R-Shiny app founded upon our novel randomized clinical trial (RCT) inequity metrics derived from machine learning fairness measures. It is designed to quantify and visualize the inequities in clinical trials and provide insights to improve the clinical trial equity and health equity, with specific considerations for diverse user groups including clinicians, researchers, and health policy advocates. 


<!-- TABLE OF CONTENTS -->
## Contents

1. [Project Description](#project-description)
1. [Application Features](#application-features)
1. [Example_Demonstration](#example-demonstration)
1. [Contact](#contact)
1. [License](#license)
1. [Acknowledgments](#acknowledgments)


<!-- ABOUT THE PROJECT -->
## Project Description
We develop the TrialEquity based on our novel RCT inequity metrics derived from Machine Learning (ML) Fairness Research. Visualizations and statistical tests based on proposed metrics enable researchers and physicians to rapidly visualize and assess potential inequities in RCTs for subgroups. The approach enables users to determine overrepresentation, underrepresentation, and exclusion of subgroups indicating potential limitations of RCTs. The method could help support evaluation of existing RCTs, design of new equitable RCTs within a given population limit, monitoring of RCT recruitment, and applicability of RCT results to patients. Additionally, TrialEquity can help the users compare the equity of different RCTs and generate larger meta-study dataset by combining several similar RCTs. For inequitable studies, TrialEquity is able to provide a remeidal suggestion through additional recruitment of participants with given addional recruiting size and interested patient attributes. Finally, individual patient equity evalution is implemented to provide information about each attribute's effect on equity for a specific patient. 

### What's the problem?
Within the field of RCT research, there has been ongoing concern that RCTs which lack a diversity of participants may not provide clear evidence of efficacy and safety for new interventions in underrepresented or missing subpopulations. To date, there has been no efficient means to quantify the inequity between those who get enrolled into RCTs and the broader population who could benefit from the new intervention.


### How can technology help?
Extensive research in ML fairness has created metrics for quantifying inequities in trained ML classification models and for creating novel ML approaches to address these inequities.

Our novel insight is that assignment of a subject to a RCT can be regarded as a classification function that is random. Applying ML-fairness metrics to this classification problem creates novel inequity metrics for RCTs and other clinical studies. The inequity metrics capture how well the actual assignment of subjects to a RCT matches of a hypothetical random assignment. Based on these metrics, ML could help the user rapidly visualize the analyze inequities of different subgroups from multiple RCTs and provide a new plan or remedial solution to improve the trial and health equity.


### The solution
We compare the observed rate in the RCT for the subgroup to the hypothetical ideal rate in an equitable RCT in which patients are assigned truly randomly to the clinical trial.  By considering assignment to the clinical trial as a random classification function, we develop standardized metrics based on variations of ML fairness metrics, such as "Log Disparate Impact." The resulting metrics are functions of disease-specific observed and ideal rates of assignment of protected subgroups to the RCT. The new equitable and remedial recruitment plans are calculated to minimize the violation of the metric thresholds and the inequity values.  

## Application Features

You can run the example studies on [**TrialEquity**]( https://miao-qi-rpi-app.shinyapps.io/TrialEquity/).

The tool can
1. Compare the RCT distribution with the target population distribution
2. Measure inequity in randomized clinical trials
3. Visualize inequity for subgroups
4. Compare inequities among studies
5. Design new equitable recruitment plans for RCTs
6. Provide remedial plans for inequitable executed/ongoing RCTs
7. Evaluate individual patient equity


<p align="center">
  <img width="50%" height="auto" src="fig0.jpg">
</p>
<p align="center">
<em></em>
</p>


## Example Demonstration
We apply the proposed RCT equity metrics to one real clinical trial Action to ControlCardiovascular Risk in Diabetes (**ACCORD**) and one self-generated RCT for demonstration. **ACCORD** data are obtained from [BiologicSpecimen and Data Repositories Information Coordinating Center (BioLINCC)](https://biolincc.nhlbi.nih.gov/home/).

<p align="center">
  <img width="50%" height="auto" src="fig1.jpg">
</p>
<p align="center">
<em></em>
</p>


<p align="center">
  <img width="50%" height="auto" src="fig2.jpg">
</p>
<p align="center">
<em></em>
</p>



<p align="center">
  <img width="50%" height="auto" src="fig3.jpg">
</p>
<p align="center">
<em></em>
</p>



<p align="center">
  <img width="50%" height="auto" src="fig4.jpg">
</p>
<p align="center">
<em></em>
</p>


<p align="center">
  <img width="50%" height="auto" src="fig5.jpg">
</p>
<p align="center">
<em></em>
</p>


<p align="center">
  <img width="50%" height="auto" src="fig6.jpg">
</p>
<p align="center">
<em></em>
</p>


<p align="center">
  <img width="50%" height="auto" src="fig7.jpg">
</p>
<p align="center">
<em></em>
</p>


<p align="center">
  <img width="50%" height="auto" src="fig8.jpg">
</p>
<p align="center">
<em></em>
</p>




<!-- CONTACT -->
## Contact

Miao Qi  - qim@rpi.edu

Project Link: [ClinicalTrialEquity](https://github.com/TheRensselaerIDEA/TrialEquityApplication)

## License

This project is licensed under the Apache 2 License

## Acknowledgments

* This work was primarily funded by IBM Research AI Horizons Network with the Rensselaer Institute for Data Exploration and Applications (IDEA)
