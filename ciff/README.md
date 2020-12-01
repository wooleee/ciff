# Causal Inference For Fairness(CIFF) Introduction
_by Woo Chul Lee, Applied Machine Learning Lab., SNU_

This github repository contains explanation including the code to analyze the fairness in datasets, as the part of my projects for Capstone Project for Data Science, GSDS of Seoul National University. It might seem elementary and easy as this is the very first milestone and entry for my research on Good AI. Deeper and more meaningful research will follow afterwards. 
***
## 1. Why CIFF?
'Causal inference' will be used for achieving 'fairness' in ML. Why these two are implemented together?

### 1.1. Fairness in ML
Fairness in Machine Learning is one of the important perspective throughout the research of AI. Suppose there is ML(including DL)model with fullfilling the state of the art accuracy, inference speed while not consuming much computational power, we might call it 'perfect model'. But if there lacks fairness and model cannot explain and unravel the itself, people won't welcomely deploy it.

Google, as part of '[Think With Google](https://www.thinkwithgoogle.com/feature/ml-fairness-for-marketers/)' project, Fairness and Trustworthiness of ML are explained as below.

> When data mirrors societal bias, it imparts a distorted view

Many of decision-making algorithms are based on the dataset. It's not common now but human being will face the era of algorithm decision-maker very soon, including banks' loan approval, corporations' hiring and prison sentences. 

Dataset is the consequence of human's decision-making. What dataset mirrors human's societal bias? To diagnose this, causal inference will be used. 


### 1.2. Causal Inference




- causal inference
- fairness
- fairness in some stages
***

## 2. What's in CIFF?
### 2.1. Diagnosis of two representative socio-economic datasets.
    1. EDA(explatory data analysis)
    2. Feature Analysis - Set Treatment, Outcome and Confounders
    3. Raise Causal Estimand
    4. Identify Estimand / Statistical Analysis through DoWhy
    5. Draw Causal Graph
    6. Diagnosis - Unfairness of Dataset

### 2.2. Functionality of mixing DoWhy and Graphviz.
  - DoWhy for Causal Inference
  - Graphviz for Causal Graph

***

## 3. Project Implementation
### 3.1. Index
#### 3.1.1. Titanic Survival Dateset
[titanic_analysis.ipynb](dfdf)
- Causal Estimand 1 $\rightarrow$ Are men preferred in risk rating(assessment) because of their sex?
- Causal Estimand 2 $\rightarrow$ Are the older preferred in risk rating(assessment) because of high age?


#### 3.1.2. German Credit Approval Dataset
[german_analysis.ipynb](dfdf)

- Causal Estimand 1 $\rightarrow$ Are men preferred in risk rating(assessment) because of their sex?
- Causal Estimand 2 $\rightarrow$ Are the older preferred in risk rating(assessment) because of high age?

<!-- 
[NLP and Sentiments Analysis based Trading Strategy](Chapter%2010%20-%20Natural%20Language%20Processing/Case%20Study%201%20-%20NLP%20and%20Sentiments%20Analysis%20based%20Trading%20Strategy/NLPandSentimentAnalysisBasedTradingStrategy.ipynb) -->



### 3.2. Environment

Next, clone this project by opening a terminal and typing the following commands (do not type the first `$` signs on each line, they just indicate that these are terminal commands):

    $ cd ~
    $ git clone https://github.com/wooleee/ciff.git
    $ cd ciff

Make env for CIFF project(Below, env name is 'ciff' for example.). If making further is impossible, install packages in existing environment, while escaping version crashes.

    $ conda create -n ciff python=3.7.9
    
Upgrade pip3 you can run the following command on Linux

    $ pip3 install --upgrade pip 

And then, using pip install all packages required(might take some minutes to install libs)  

    $ conda activate ciff
    $ python3 -m pip install --upgrade -r requirements.txt



***

## 4. References

### 4.1. Libs
### 4.2. Datasets
- German Credit Approval: https://www.kaggle.com/kabure/german-credit-data-with-risk
- Titanic Survival: 

### 4.3. Papers

### 4.4. Books


### 4.5. Others
- https://www.thinkwithgoogle.com/feature/ml-fairness-for-marketers/#what-is-data-bias