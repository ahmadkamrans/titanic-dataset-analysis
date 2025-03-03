# Titanic Dataset Analysis

## **Overview**
- The **Titanic Dataset** contains the detailed information about the passenger's aboard on it, which sank during its first commute on **April 15, 1912**. After colliding with the **ice-berg**. 
- The primary objective of analyzing this dataset is to extract some useful insights for the passenger survival on vairous features.

#### **Columns**
The dataset includes the following columns:

- **PassengerId:** A unique identifier for each passenger
- **Survived:** Indicated if the passenger suvived (1) or, not (0)
- **Pclass:** Ticket Class for the passengers aboard (1st, 2nd, 3rd)
- **Name:** Passenger's full name
- **Sex:** Gende of the passenger
- **Age:** Age of the passenger
- **Sibsp:** Number of sibling, spouses
- **Parch:** Number of Parents, children
- **Ticket:** Ticket Number
- **Fare:** Passenger fare
- **Cabin:** Cabin number (some are mentioned in dataset in series like B1-B10)
- **Embarked:** Port of embarkation (C for Cherbourg, Q for Queenstown, S for       Southhampon)

## Cleaning of Dataset

As now we have a basic knowledge of what dataset is about, and on which columns the whole dataset is comprised of. Let's start cleaning the dataset: 

- Our dataset is comprised of 11 columns with total 891 entries for each column.

![alt text](images/image.png)

- Now let's see the columns where the entries are not 891. But instead they have missing/null values in those columns. The findings were: 
 - Age, Cabin, and Embarked entries were missing

![alt text](images/image%201.png)

- Count of the missing values in the mentioned columns above:
  1. Age has 177 missing entries
  2. Cabin has 687 missing entries
  3. Embarked has 2 missing entries

![alt text](images/image%202.png)

#### Identified Columns cleaning

Now as till now we have identified the problematic columns lets proceed with cleaning of the one by one.

##### AGE: 
- As the age column has numerical data. A better insight into it is by using the describe which will give us the mean, median, max, quartiles for the box plot. 

![alt text](images/image%203.png)

- The median age is 28 years

![alt text](images/image%204.png)

- Before deciding anything let's plot a simple histogram to see what the age distribution looks like on raw data.

![alt text](images/image%205.png) 

 Here we can see that the our data is not either skewed to the left, or right. But close to symmetrical. Making a good balanced mountain hill. If you try to make it by drawing the a one line through all the bars on there top. 
 On raw data before cleaning, the most high distributed age is between late 20's to 30.

---

## Dataset Used
[Titanic Dataset (Kaggle)](https://www.kaggle.com/c/titanic/data)

The dataset consists of passenger details such as age, gender, ticket class, fare, and survival status.

- **`train.csv`** → Used for analysis & training (Contains `Survived` column)