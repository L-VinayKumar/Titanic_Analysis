# **To predict a classification - survival or deceased**

The sinking of the Titanic is one of the most infamous shipwrecks in history.

On April 15, 1912, during her maiden voyage, the widely considered “unsinkable” RMS Titanic sank after colliding with an iceberg. Unfortunately, there weren’t enough lifeboats for everyone onboard, resulting in the death of 1502 out of 2224 passengers and crew.

While there was some element of luck involved in surviving, it seems some groups of people were more likely to survive than 




![App Screenshot](https://pngimg.com/uploads/titanic/titanic_PNG34.png)
Full report of this project: [Titanic](https://github.com/L-VinayKumar/Titanic_Analysis/tree/main/Titanic_analysis)

## Table of Contents:

    1. Objective
    2. Data understanding
    3. Prerequisite
    4. Exploratory Data Analysis
    5. Data Visualization
    6. Data Cleaning
    7. Model Building 
    8. Evaluation Results
    9. Conclusion


### Objective:
To predict a classification - survival or deceased and implementing Logistic Regression Model for classification with "semi-cleaned" version of the titanic data set

Building a predictive model that answers the question: “what sorts of people were more likely to survive?” using passenger data.
## Data understanding

* 	survival	:   Survival

                -> 0 = No
                -> 1 = Yes
*   pclass	 :     Ticket class

                -> 1 = 1st
                -> 2 = 2nd
                -> 3 = 3rd
*   sex	    :    Sex	
*   Age	Age  :   in years	
*   sibsp	 :   # of siblings / spouses aboard the Titanic	
*   parch	 :   # of parents / children aboard the Titanic	
*   ticket	 :   Ticket number	
*   fare	 :   Passenger fare	
*   cabin	 :   Cabin number	
*   embarked :	Port of Embarkation

                -> C = Cherbourg 
                -> Q = Queenstown
                -> S = Southampton
       




## Prerequisite :
_pandas package :_

> $ sudo pip install pandas

_seaborn package :_

> $ sudo pip install seaborn

_matplotlib package :_

> $ sudo pip install matplotlib

sklearn package :_

> $ sudo pip install sklearn


## Exploratory Data Analysis
At this stage, a brief analysis of the data will be carried out,

    1. Check the missing data
    2. Data Visualization
    3. Data Cleaning
    4. Check missing values again

## Data Visualization

    * Survived according to the Passenger Class
  ![Logo](https://github.com/L-VinayKumar/Titanic_Analysis/blob/main/Titanic_analysis/Survived_according_pclass.png?raw=true)

    * Age in years
  ![Logo](https://github.com/L-VinayKumar/Titanic_Analysis/blob/main/Titanic_analysis/Age_in_years.png?raw=true)

    * Average Age by Passenger Class
  ![Logo](https://github.com/L-VinayKumar/Titanic_Analysis/blob/main/Titanic_analysis/avg_age_pclass.png?raw=true)


## Data Cleaning

* Fill in missing age data instead of just dropping the missing age data rows by mean age of all the passengers
* Using average age values to impute based on Pclass for Age.
* Drop cabin column and the rows in Embarked that is NaN
* Need to convert categorical features to dummy variables! Otherwise our machine learning algorithm won't be able to directly take in those features as inputs.

  ![Logo](https://github.com/L-VinayKumar/Titanic_Analysis/blob/main/Titanic_analysis/data_clean.png?raw=true)

## Model Building

* Building a Regression Model
* Using Train-Test Split
* Training and Predicting
* Logistic regression model is used for prediction

## Evaluation Results

* Using classification report, we can check precision,recall,f1-score

![Logo](https://github.com/L-VinayKumar/Titanic_Analysis/blob/main/Titanic_analysis/Evaluation_results.PNG?raw=true)

## Conclusion

Our complete analysis mainly covered three factors in this analysis (Age, Sex, Pclass).

Age: Doesn't play much role in determining the survival chances, except for ages below 1 years.

Sex: Women had better chances of survival than men.
In general, Women & children across all classes had higer survival rates than men.

Pclass: Pclass-1 had best while Pclass-3 has the worst survival rate.
So we can say, that being a women in Pclass-1 seems to have the best chances of survival. However being a child or woman could not be considered as 100% survival chance.

### Limitations

The Age data was incomplete. Almost 20% of the age values were missing. We chose to impute average age values based on Pclass for age.
Since we didnot have a clear age demarcation for children vs adults, we assumed the cutt off value for age of chidren as 16 years.
