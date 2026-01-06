# Introduction 
This repository contains the data and code associated with the manuscript **"More Signal vs. More Noise - Comparing Full Text and Abstract as Inputs for Large Language Model–based Classification of Oncology Trial Eligibility Criteria"**.
The objective of this analysis was to assess whether GPT-5 performs better in classifying oncology trials according to eligibility of patients with localized vs. metastatic disease when provided with the full text compared to the abstract only.

# Data
The sample of 200 trials was drawn from the combination of the *test* and *train* dataframes originally created for the study [Metastatic vs. Localized Disease As Inclusion Criteria That Can Be Automatically Extracted From Randomized Controlled Trials Using Natural Language Processing](https://github.com/windisch-paul/metastatic_vs_local) where they were used to train and test a machine learning model.

Each trial corresponds to one row in a CSV file. Columns represent different attributes of each publication (e.g. DOI, abstract, full text, annotations).

Relevant columns for the present analysis:
- __doi__: Digital Object Identifier of the trial
- __title__: Title of the trial according to PubMed
- __abstract__: The abstract of the trial
- __full_text__: The full text of the trial
- __family__: Classification into tumor entities
- __accept__: Ground-truth labels assigned independently by two human annotators
  - “LOCAL”: Inclusion of patients with localized disease  
  - “METASTATIC”: Inclusion of patients with metastatic disease  
  - Both labels: Trials allowing inclusion of both patient groups  
  - No label: Screening or prevention trials without known cancer  
- __abstract_gpt-5-2025-08__:Labels that were assigned by GPT-5 based on the abstract
- __full_text_gpt-5-2025-08__:Labels that were assigned by GPT-5 based on the full text
