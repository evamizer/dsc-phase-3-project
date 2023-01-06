# Phase 3 Diabetes Screening

Welcome prospective doctors, nurses, and beyond! For my third phase project in the Flatiron Data Science program, I have made a model that can help screen patients for diabetes. 

In this project description, we will cover:

* [***Project Overview:***](#project-overview) The project goal, audience, and dataset
* [***Deliverables:***](#deliverables) The specific items I produced for this project
* [***Basic Walkthru:***](#basic-walkthru) The basics of what I did during the project
* [***Findings/Business Recommendations:***](#findings-rec) Important features and recommendations based on those
* [***Beyond:***](#beyond) What I'd like to do to improve further


## Project Overview<a id='project-overview'></a>

For this project, I used exploratory data analysis, data preparation, and modeling to generate insights for a business stakeholder.

### Business Problem

#### Stake Holders:
* Medical facilities such as primary care physician offices, or even other medical care facilities such as convenient care facilities, urgent care facilities, and hospitals. While these are my primary stake holders, it would be within the rhealm of possibility that this model could be used by insurance companies.

#### Busniess Problem/Solution:
* When receiving a new patient or even reviewing updated information for a current patient, doctors and nurses would be able to input the basic data points needed for the model to see if a patient might have diabetes (diagnosed or not). 

#### Performance Goals:
* **My goal is to make predictions with my model as accurately as possible while maximizing true positive cases. We will be setting our thresholds at 80% for both Mean Cross Validated Roc_Auc Score and Recall.** 

* Since this is just a quick tool to screen if someone is likely to have diabetes, it would be better to cast a wider net and overdiagnose than to underdiagnose. Undiagnosed diabetes can have pretty serious health complications if left untreated, so overdiagnosing (high recall for true positives even at the expense of true negatives recall) would be advised. Doctors can order more specific tests to determine if someone does indeed have diabetes. 

* **It should be noted that this model does not distinguish between Type-1 and Type-2 diabetes.**

### The Datasert

The [data]("https://www.kaggle.com/datasets/prosperchuks/health-dataset") we are using today is from the [Behavioral Risk Factor Surveillance System (BRFSS)](https://www.kaggle.com/datasets/cdc/behavioral-risk-factor-surveillance-system"), a health-related telephone survey that is collected annually by the CDC. This dataset is a balanced subset of the original dataset of 441,455 Americans on health-related risk behaviors, chronic health conditions, and the use of preventative services from 2015, made available on Kaggle. These features are either questions directly asked of participants, or calculated variables based on individual participant responses. While the original dataset had over 330 features and over 400,000 entries, this subset has 21 feature variables and 70,692 entries. Because the subset is so large, we will be take a 10% sample of that subset for ease of use.

It should be noted that this dataset does not distinguish between Type-1 and Type-2 diabetes.

## Deliverables<a id='deliverables'></a>

There are three deliverables for this project:

* A **non-technical presentation** (added as a pdf)
* A **Jupyter Notebook**
* A **GitHub repository**

## Basic Walkthru<a id='walkthru'></a>

* **Exploring the data**: sizing up the data, planning what needs to be done
* **Cleaning/Preprocesing the data**: No cleaning needed, so we made a representative subset of the subset, and checked for multicolinearity/correlation. Then I picked some variables to look at and examined how they compared in people with and without diabetes. 
* **Data Prep/Feature Engineering**: Firstly, I ohe-ed the variables that weren't already in the binary format, and combined it with those already in 1/0 format. Then, I assigned the target variable to Y and the rest to X, and split the data into my test and training sets. 
* **Models**: I tried out a few different models (Logistic Regression*, Decision Tree Model*, XG Boost*, AdaBoost**, and LogitBoost), adding in analysis for each one and trying out different ways to improve their results.
* **Final Model Selection**: Review the model I selected and explain why I chose it. 
* **Business Recommendations** - Implimentation and greater uses. 
* **Beyond**: Relfections on how I would improve my process or do something differently in the future. 

Note:

 ***"*"***= Model was optimized with GridSearchCV after baseline established
 ***"**"= Model was optimized with SVC after baseline established

## Findings/Business Recommendations <a id='findings'></a>

**Basic Use Function**
When receiving a new patient or even reviewing updated information for a current patient, doctors and nurses would be able to input the basic data points needed for the model to see if a patient might have diabetes (diagnosed or not). This can be implimented into their workflow via an add-on to software they currently use, or as a standalone application.

**What next?**
While this model can be useful for inputting data on new and existing patients, it shows that the most influental parameters could be examined to utilize in an action plan to improve the patients health.
For example, while someone cannot make themselves younger or erase a stroke from their medical history, they could work to:

* get their BMI to a healthy level
* lower their blood pressure
* take steps to improve their general physical health
* refer to mental health services such as counseling, therapy, etc. as needed

## Beyond<a id='beyond'></a>
I would like to explore the original data from the original dataset (rather than this subset) and do a bit more exploratory analysis on that. This dataset explored pretty broad topics, but I'd like to see if going into more detail in each topic made more of a difference rather than the broad topic on it's own.

In addition, I would like to explore more data derived not from the patients opinion, but from a measurable quantity outside of that to see if we can get away from possible personal bias.

On a more data-centric note, I think next time I will change the column titles after OHE-ing, as continually refering back to my legend got pretty old, pretty fast. 

