# HR Analytics Classification: Project Overview
* Build model to help HR team to filter the eligibility of employees for promotion process
* This dataset is obtained from [HR_Analytics_Classification | Kaggle](https://www.kaggle.com/bhrt97/hr-analytics-classification)
* Cleaned the data from missing value with `mode()` for education's feature and `median()` for previous_year_rating's feature
* Engineered features to optimizing the learning process of model
* Train model with 5 different algorithms, and choose the top 3 for next hyperparameter tuning
* *Handle imbalanced class with `scale_pos_weight`(only for XGBoost)*
* Validate the model with data test 

## Problems
* Currently, **the processing & analysis** the employees data has been **largely manual to filter the eligibility** of employees for promotion, and this **leads to delay** in transition to the new roles after promotion
* With a large time and manual process, processing & analysis are also **may be less accurate**

## Purposes
**Reduce the flow** of processing & analysis **to filter the eligibility** of employees with a **more automated process & more accurate**

# Early Insight from The Data
1. Distribution of Promoted Employees is not Balanced<br>
![alt text](https://github.com/Jomen034/HR_Analytics_Classification/blob/master/fig/Distributin%20of%20Promoted%20and%20Not%20Promoted%20Employees.png "Distributin of Promoted and Not Promoted Employees")<br>
2. Employees who achieved their KPIs >80% have higher probabilities to get promotion<br>
![alt text](https://github.com/Jomen034/HR_Analytics_Classification/blob/master/fig/Probability%20based%20on%20KPI.png "Probability based on KPI")
3. Employees with award(s) also have the higher chance to get promotion<br>
![alt text](https://github.com/Jomen034/HR_Analytics_Classification/blob/master/fig/Probability%20based%20on%20awards_won.png "Probability Based on Awards")
4. Uniquely, employees with average training score is >=90 almost all of them get promotion
5. Higher the rating, higher the chance to get promotion<br>
![alt text](https://github.com/Jomen034/HR_Analytics_Classification/blob/master/fig/Probability%20based%20on%20previous_year_rating.png "Probability based on Previous Year Rating")

# ML Modeling
Before train the model, split the data into train set & test set (size is 20%).
Trained the model with 5 different algorithms and evaluated them with **F1-Score**. The reason is to **reduce** the False Positive and False Negative. This is for good filtering, and in the end, HR can minimized the wrong predictions than can lead to another issues likeemployee churn for wrong not-promoted, and not well-perform for wrong promoted. The model was trained with:
* Decission Tree
* Random Forest
* KNN
* Logistic Regression
* XGBoost

# Model Evalutaion
The model were evaluated with **F1-Score**. Choose the top 3 F1-Score for the next hyperparameter.
| Model | F1-Score | Difference Between Test & Train Score |
| --- | --- | --- |
| **Decision Tree** | **28.50%** | **0.17%** |
| **Random Forest** | **47.40%** | **1.31%** |
| **XGBoost** | **53.20%** | **0.20%** | 

# Business Insight & Recomendations
1. Performance Level (enginereed feature) can meassure the chance for employees eligibility<br>
![alt text](https://github.com/Jomen034/HR_Analytics_Classification/blob/master/fig/Probability%20based%20on%20performance_level.png "Probability based on Performance Level")
Improve employee performance by engaging them to achieve KPIs, take well-scored trainings, get award(s), and get high rating
2. **Current features don’t have good pattern** for promoted employees. **Consider** to **add new features** to optimizing the identification process
3. **Give feedback** to not promoted employees about why they didn’t get promoted
4. **Build user-friendly web app** to operate the model **if then the model will be implemented**

# Team Behind This Project
* As the final project to finish learning path for Data Science in [Rakamin_Academy](https://rakamin.com/), this model was built from a growth team called **Hi5**<br>

**The Team Member**<br>
| Member | email | Phone Number | LinkedIn url |
| --- | --- | --- | --- |
| **Our Friendly Mentor: Ade Irawan** | - | +6281906486000 | - |
| **Jomen Pardede (me)** | jomenpardede@gmail.com | +6282272055282 | www.linkedin.com/in/jomen-pardede |
| **Herdin Surya Dwi Putra** | herdinsurya@gmail.com | +6281272243710 |  www.linkedin.com/in/herdinsurya |
| **Mia Maryasha** | maryashamia@gmail.com | +6281285566246 | www.linkedin.com/in/mia-maryasha-738723173 |
| **M. Jayus Abror** | mhmdabror1994@gmail.com | +6282211101091 | www.linkedin.com/in/mohammad-ardiansyah-gonti-266706110 |
| **Moh. Ardiansyah Gonti** | - | +6285717368356 | www.linkedin.com/in/mohammad-ardiansyah-gonti-266706110 |
