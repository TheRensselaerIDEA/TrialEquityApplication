# TrialEquity Prototype

[![License](https://img.shields.io/badge/License-Apache2-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0) 


[**TrialEquity**]( https://miao-qi-rpi-app.shinyapps.io/TrialEquity/) is an interactive web-based R-Shiny prototype founded upon our novel randomized clinical trial (RCT) equity framework inspired by machine learning fairness. It is designed to quantify, visualize, and reduce inequities in clinical trials and thus provide insights to improve clinical trial equity and health equity, with specific considerations for diverse user groups including clinicians, researchers, and health policy advocates. 


<!-- TABLE OF CONTENTS -->
## Contents

1. [Project Overview](#project-overview)
1. [Application Features](#application-features)
1. [Example Demonstration](#example-demonstration)
1. [Contact](#contact)
1. [License](#license)
1. [Acknowledgments](#acknowledgments)


<!-- ABOUT THE PROJECT -->
## Project Overview
We develop the TrialEquity based on our novel RCT equity framework derived from machine learning (ML) fairness research. The prototype helps clinical
researchers, healthcare providers, and policy makers to address the needs and improve the care of underserved populations. TrialEquity is designed for two types of users: researcher and physician, who are interested in different topics related to health equity. It provides three capabilities for each type of users.
For researchers, "Equity Evaluation" allows them to measure equity levels of RCT subgroups defined over selected patient characteristics; "Comparative Study of
Equity" allows users to compare equities of a set of subgroups of interest among different RCTs; "Enrollment Planning" helps provide an equitable recruitment plan for RCTs. "Enrollment Planning" enables our approach to be applied to three different cases: "New Enrollment Planning" gives a new equitable enrollment plan for any single-site RCTs at design/planning stage; "Monitor Enrollment" makes a remedial re-planning recruitment plan for ongoing/executed single-site RCTs if inequities are identified; "Multi-site Enrollment Planning" designs an equitable enrollment plan with site selection for multi-site RCTs. For physicians, "Study vs Target Population" compares subjects’ distribution of RCT sample to that of target population; “Equity Evaluation” is the same as the function for researchers; "Patient-Specific Equity" calculates equity score of an individual patient regarding to different RCTs and identifies the effect of each selected characteristic on this patient-specific equity score.

<p align="center">
  <img width="80%" height="auto" src="/Figures/toolArch.png">
</p>
<p align="center">
<em>Overview of TrialEquity functionalities.</em>
</p>



### What's the problem?
Within the field of clinical research, there has been ongoing concern that RCTs which lack a diversity of participants may not provide clear evidence of efficacy and safety for new interventions in underrepresented or missing subpopulations. The NIH and other federal agencies have promoted policies and efforts to improve clinical trial recruitment of underserved populations. However, no current technology solutions designed to solve problems related to heath equity exist to systematically evaluate equity of clinical trial participation.


### How can technology help?
Extensive research in ML fairness has created metrics for quantifying inequities in trained ML classification models and for creating novel ML approaches to address these inequities.

Our novel insight is that assignment of a subject to an RCT can be regarded as a classification function that is random. Applying ML-fairness metrics to this classification problem creates novel inequity metrics for RCTs and other clinical studies. The inequity metrics capture how well the actual assignment of subjects to an RCT matches of a hypothetical random assignment. Based on these metrics, ML could help the user rapidly visualize the analyze inequities of different subgroups from multiple RCTs and provide a new plan or remedial solution to improve the trial and health equity.


### The solution
We compare the observed rate in the RCT for the subgroup to the hypothetical ideal rate in an equitable RCT in which patients are assigned truly randomly to the clinical trial.  By considering assignment to the clinical trial as a random classification function, we develop standardized metrics based on variations of ML fairness metrics, such as "Log Disparity." The resulting metrics are functions of disease-specific observed and ideal rates of assignment of protected subgroups to the RCT. The new equitable and remedial recruitment plans are calculated to minimize the violation of the metric thresholds and the inequity values.

We also proposed a multi-objective goal-programming (GP) model for equitable enrollment planning and monitoring based on our equity framework. Guided by the scientific aims of the study, our GP model explicitly models equitable representation as a goal in enrollment and allows researchers to set goal preferences/priorities that best fit the applied scenario and learn from intermediate analysis to obtain a more satisfying solution eventually. Enrollments goals for subgroups defined on the basis of sex/gender, race/ethnicity, age, or other desired characteristics are defined using surveillance datasets.
Thus, the GP modeling process provides justification in terms of a representative sample required by NIH and IRB evaluation to perform valid analysis. It also incorporates lower bounds on subgroup sizes to ensure that the study has sufficient power to determine subgroup differences.

Building on our equity framework, which can systematically evaluate how significantly different the characteristics of the cohort participating in clinical trials are from population-level, disease-specific estimates of those characteristics in national samples, we have implemented a web-based TrialEquity prototype to address the equity problem of clinical research for diverse user groups, and thus promote health equity. Since most medically underserved populations are heterogeneous in composition, our prototype allows for the multivariate analysis on different numbers of population characteristics, which provides more precise and profound insights on equity issue of poor and underserved populations in clinical research. For example, an intervention beneficial for White participants may produce different health outcomes if the gender or age of the same White subjects are taken into account.




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


## Example Demonstration
We apply the proposed RCT equity metrics to a real clinical trial Action to Control Cardiovascular Risk in Diabetes (**ACCORD**) for single-RCT analysis and Antihypertensive and Lipid-Lowering Treatment to Prevent Heart AttackTrial (**ALLHAT**), and Systolic Blood Pressure Intervention Trial (**SPRINT**) for multiple-RCT comparison. All sample data are obtained from [Biologic Specimen and Data Repositories Information Coordinating Center (BioLINCC)](https://biolincc.nhlbi.nih.gov/home/).

TrialEquity is designed for two types of users, researchers and physicians, to perform different tasks based on different interests of the users. To start the
analysis, users should indicate a user type based on their roles.
<p align="center">
  <img width="80%" height="auto" src="/Figures/userType.png">
</p>
<p align="center">
<em>User type selection of TrialEquity.</em>
</p>

The following three figures are snapshots of the target population information and RCT upload page. The application allows user to upload multiple target population datasets and RCT datasets for different diseases and to apply single RCT evaluation and multiple RCTs analysis at the same time. 
<p align="center">
  <img width="80%" height="auto" src="/Figures/targetUpload.png">
  <img width="80%" height="auto" src="/Figures/targetUpload2.png">
</p>
<p align="center">
<em>Upload page for target population information in TrialEquity. Top: Default target population estimated from NHANES. Bottom: User-uploaded target population file.</em>
</p>


<p align="center">
  <img width="80%" height="auto" src="/Figures/rctUpload.png">
</p>
<p align="center">
<em>Upload page for RCT information in TrialEquity.</em>
</p>



The two figures below demonstrate the distributions of patients from different gender, age, race/ethnicity, and education level groups in an RCT and the target population. The figures clearly identify that young patients are missing from the clinical trial. Also, the higher red bin shows that the subgroup may be overrepresented in the RCT (e.g. non-Hispanic black female participants aged 45-64 and have high school degree), while the higher green bin shows that the subgroup has the potential to be underrepresented in the RCT (e.g. Hispanic female participants aged 45-64 and do not graduate from high school). The wider green bin means that the subgroup is missing from the clinical trial (e.g. female participants aged 18-44). As shown in the top figure, the plot is interactive and the detailed group information will show up when the mouse hovers on the bin. More interactive functions are shown on the up-right corner on the bottom figure. For example, when the distributions are characterized by a large number of attributes, some bins are too small to be examined and the "zoom in" function can perfectly solve this problem.
<p align="center">
  <img width="80%" height="auto%" src="/images/fig1.PNG">
</p>
<p align="center">
<em>Interactive distributions of subgroups defined over gender, age, race/ethnicity, and education level in both target population and RCT.</em>
</p>


<p align="center">
  <img width="80%" height="auto" src="/images/fig2.PNG">
</p>
<p align="center">
<em>Using zoom in function to examine distributions of subgroups defined over gender, age, race/ethnicity, and education level in both target population and RCT.</em>
</p>


In our visualization, grey indicates that no people with selected protected attributes exist in the target population; black means that the subgroup is missing in both target population and RCT; dark red represents the absent subgroup from the RCT; orange-red and yellow-brown point out that some subgroups are not sufficiently represented and may be at risk of being insufficiently recruited into and represented in the clinical trial cohort; on the other hand, dark blue and light blue identify the potential advantaged subgroups which may make inefficient treatment seem helpful or vice versa; teal shows that the subgroup is equitably represented in the clinical trial. 

<p align="center">
  <img width="60%" height="auto" src="/images/colorLegend.png">
</p>
<p align="center">
<em>Color representation of inequity levels</em>
</p>

The next figure presents the equity levels of subgroups defined by gender, age, and race/ethnicity, and education level from the inner ring to the outer ring using the Log Disparate Impact metric. By hovering the mouse on a subgroup area of interest on the sunburst, the equity label, ideal rate, observed rate, and real number of participants of the subgroup will show on the screen. Additionally, by clicking in subgroup area on the sunburst, the corresponding math function of observed rates will show on the right side of the screen. The green line indicates the ideal rate and the brown line indicates the current RCT observed rate on the figure. The order of attributes shown above the sunburst figure can be rearranged to generate different figures for other subgroups. Also, additional equity metrics including Adjusted Equal Opportunity and Quality Metric can be applied for evaluation.

<p align="center">
  <img width="80%" height="auto" src="/images/fig3.png">
</p>
<p align="center">
<em>The Log Disparate Impact equity levels of subgroups defined over gender, age, and race/ethnicity, and education level, with the corresponding function of observed rate for subgroup Non-Hispanic female susbjects aged over 64 and have some college education in ACCORD, with significance level = 0.05, lower equity threshold = 0.2, and upper equity threshold = 0.4.</em>
</p>


The two figure below compare two RCTs, SPRINT and ALLHAT, of hypertension on univariate analysis. We can first compare the equity levels by colors and then go to details by examining the numerical values of equity. For the two RCTs shown here, the ALLHAT RCT is more equitable than the SPRINT regarding to attributes such as gender since more subgroups are fallen into the equitable level and have lower values. A meaningful comparison usually happens for studies of the same disease.
<p align="center">
  <img width="80%" height="auto" src="/images/fig4.PNG">
</p>
<p align="center">
<em>Study comparison on univariate analysis between two hypertension RCTs on patient clinical characteristics.</em>
</p>


<p align="center">
  <img width="80%" height="auto" src="/images/fig5.PNG">
</p>
<p align="center">
<em>Study comparison on univariate analysis between two hypertension RCTs on patient demographic characteristics.</em>
</p>

Our application can design an equitable recruitment plan for new studies with the given expected number of participants and the attributes that are interested by the researchers. The result is displayed as a table for each subgroup. The sunburst figure will show the equity level of this new plan. The following figures clearly shows that the new recruitment plan is equitable for all subgroups. 
<p align="center">
  <img width="80%" height="auto" src="/images/fig6.PNG">
</p>
<p align="center">
<em>New recruitment plan for a type-2 diabetes RCT of 1000 participants with protected attributes gender, age, and race/ethnicity using Log Disparate Impact metric.</em>
</p>


<p align="center">
  <img width="80%" height="auto" src="/images/fig6_2.PNG">
</p>
<p align="center">
<em>Equity level on subgroups defined by age and race/ethnicity by following our suggested recruitment plan using Log Disparate Impact metric.</em>
</p>

Instead of providing an equitable recruitment plan for new studies, our application helps improve the equity of executed/ongoing RCTs through additional recruitment. The result is displayed as a table on the left. The middle sunburst figure demonstrates the inequity situation of subgroups in the old RCT. The right sunburst figure shows the new inequity situation after the additional recruitment. For the figure below, many originally inequitably represented subgroups are shown to be equitable with 1000 more participants. 
<p align="center">
  <img width="80%" height="auto" src="/images/fig7.PNG">
</p>
<p align="center">
<em>Remedial additional recruitment plan of 1000 participants for the ACCORD with protected attributes age and race/ethnicity using Log Disparate Impact metric.</em> 
</p>

<p align="center">
  <img width="80%" height="auto" src="/images/fig7_2.PNG">
</p>
<p align="center">
<em>Comparison of equity levels on subgroups before and after remedial recruitment for ACCORD on 1000 participants on protected attributes age and race/ethnicity using Log Disparate Impact metric.</em> 
</p>

Finally, the application assesses the equity condition of an individual patient. The following snapshots shows that a patient who is male, Hispanic, aged over 64, with some college/technical school degree, has systolic blood pressure between 130-139, and normal weight is highly underrepresented in the RCT with a equity score lower than -5. The diverging bar chart analyzes that the inequitable situation is mainly caused by the race/ethnicity factor "Hispanic", and also his BMI and age. Other attributes either make him equitably represented or overrepresented.

<p align="center">
  <img width="80%" height="auto" src="/images/fig8_2.PNG">
</p>
<p align="center">
<em>Individual patient equity score for a male Hispanic subject who is over 64, with some college/technical school degree, has systolic blood pressure between 130-139, and normal weight. </em>
</p>

<p align="center">
  <img width="80%" height="auto" src="/images/fig8.PNG">
</p>
<p align="center">
<em>Individual patient equity evaluation for a male Hispanic subject who is over 64, with some college/technical school degree, has systolic blood pressure between 130-139, and normal weight. </em>
</p>






<!-- CONTACT -->
## Contact

Miao Qi  - qim@rpi.edu / qimiaorpi@gmail.com

Project Link: [ClinicalTrialEquity](https://github.com/TheRensselaerIDEA/TrialEquityApplication)

## License

This project is licensed under the Apache 2 License

## Acknowledgments

* This work was primarily funded by IBM Research AI Horizons Network with the Rensselaer Institute for Data Exploration and Applications (IDEA)
