# Causal Inference For Fairness(CIFF) Introduction
_by Woo Chul Lee, Applied Machine Learning Lab., SNU_

This github repository contains explanation including the code to analyze the fairness in datasets, as the part of my projects for Capstone Project for Data Science, GSDS of Seoul National University. (It might seem elementary and easy as this is the very first milestone and entry for my research on Good AI. Deeper and more meaningful research will follow afterwards.) After reading and looking through all of my project content, you could see graphical anaysis of fairness by causal inference, as example below.

<img src = "/assets/ex.gif" width = 400>

***
## 1. Why CIFF?
'Causal inference' will be used for achieving 'fairness' in ML. Why these two are implemented together?

### 1.1. Fairness in ML
Fairness in Machine Learning is one of the important perspective throughout the research of AI. Suppose there is ML(including DL)model with fullfilling the state of the art accuracy, inference speed while not consuming much computational power, we might call it 'perfect model'. But if there lacks fairness and model cannot explain and unravel the itself, people won't welcomely deploy it.

Google, as part of '[Think With Google](https://www.thinkwithgoogle.com/feature/ml-fairness-for-marketers/)' project, Fairness and Trustworthiness of ML are explained as below.

> When data mirrors societal bias, it imparts a distorted view

Many of decision-making algorithms are based on the dataset. It's not common now but human being will face the era of algorithm decision-maker very soon, including __banks' loan approval, corporations' hiring and prison sentences__. 

Dataset is the consequence of human's decision-making. What dataset mirrors human's societal bias? To diagnose this, causal inference, which is the best tool for alleviating bias, will be used. 


### 1.2. Causal Inference(CI)
 Even there were many definitions of fairness and fairness of the machine learning model were scrutinized in many [ways](https://fairware.cs.umass.edu/papers/Verma.pdf), we cannot just say there is 'bias' in the dataset according statistical analysis of model outputs, including analyzing confusion matrix, calculating calibrations scores. 

But, let's suppose we find that the output is caused by the difference of protected features? The situation that protected features(treatment in CI) are causing the consequence(outcome in CI) to be different is the most direct proof of unfairness. That could be accomplished by causal inference, even considering confounding features that influence both treatment and outcome. Let's see how it does.

***

## 2. What's in CIFF?
### 2.1. Diagnosis of two representative socio-economic datasets.  

Project will be completed by process below;

1. EDA(explatory data analysis)
2. Feature Analysis - Set Treatment, Outcome and Confounders
3. Raise Causal Estimand
4. Identify Estimand / Statistical Analysis through DoWhy
5. Draw Causal Graph
6. Diagnosis - Unfairness of Dataset

### 2.2. Functionality of mixing DoWhy and Graphviz.
  - DoWhy for Causal Inference
  - Graphviz for Causal Graph

#### 2.2.1. `analysis` function
Analysis function returns 'the graph with annotated ATE in the edge'. 
- __Treatment__(sex) and __outcome__(risk) are expressed in the __square__. 
- __Confounders__(jobs, savings account, etc.,) are in __circle__. 
- As confounding variable is selected by person who analyze, we cannot say that there is no __latent confounding variable__. That was expressed as __black circle__.

<img src = "/assets/causalgraph.png" width = 600>

***

## 3. Project Implementation
Datasets and examples are in this repo., which are easily executed by users who follow below steps.

### 3.1. Index
Two socio-economic datasets were analyzed. 

#### 3.1.1. Titanic Survival Dateset
[titanic_analysis.ipynb](analysis/titanic_analysis.ipynb)
- Causal Estimand 1 &#8594;	 Is more men `died` because of their `gender`?
- Causal Estimand 2 &#8594;	 Are people `died` because they were sitting in the low `class`?
- Causal Estimand 3 &#8594;	 Did `the number of families` cause the `survival`?

#### 3.1.2. German Credit Approval Dataset
[german_analysis.ipynb](analysis/german_analysis.ipynb)

- Causal Estimand 1 &#8594;	 Are men preferred in `risk rating`(assessment) because of their `sex`?
- Causal Estimand 2 &#8594;	 Are the older preferred in `risk rating`(assessment) because of high `age`?

### 3.2. Environment
Clone this project by opening a terminal and typing the following commands(please don't type the first `$` signs on each line, they just indicate that these are terminal commands):

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
- DoWhy: https://microsoft.github.io/dowhy/
- Graphviz: https://graphviz.readthedocs.io/en/stable/manual.html

### 4.2. Datasets
- German Credit Approval: https://www.kaggle.com/kabure/german-credit-data-with-risk
- Titanic Survival: https://www.kaggle.com/c/titanic-survival

### 4.3. Papers

- Fairness Definitions Explained, Sahil Verma: https://fairware.cs.umass.edu/papers/Verma.pdf

### 4.4. Books
- The Book of Why, Judea Pearl and Dana Mackenzie: https://www.amazon.com/Book-Why-Science-Cause-Effect/dp/046509760X
- Causal Inference in Statistics: A Primer, Judea Pearl and Madelyn Glymour: https://www.amazon.com/Causal-Inference-Statistics-Judea-Pearl/dp/1119186846

### 4.5. Others
- Introduction to Causal Inference, Brady Neal: https://www.bradyneal.com/causal-inference-course
- Think with Google, Google: https://www.thinkwithgoogle.com/feature/ml-fairness-for-marketers/#what-is-data-bias
