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

 Here we can see that the our data is not either **skewed** to the left, or right. But close to **symmetrical**. Making a good balanced mountain hill. If you try to make it by drawing the a one line through all the bars on there top. 
 On **raw data** before cleaning, the most high age count in result of the distribution is between **late 20's to 30**.

-  Now there are two approaches to go with:
   1. If the skewness value is:
      - greater than 1
      - less than -1
    then simply replace the missing/null values with the **mean**
   2. If skewness value is:
      - close to zero 
    then simply replace the missing/null values with **median**

- In our case, we decided to go with the mean. As, out skewness value is: 

![alt text](images/image%206.png)  

 Thi case the value was close to zero, meaning symmetrical. So, we replaced the missing values with mean resulting in this histogram: 

![alt text](images/image%207.png)

##### Insights of the AGE: 
1. **Peak at 30 Years:** 
    - We can see the highest bar is around the **30 years**. Which aligns with the **mean (29.7)** used for missing data imputations.
    - THe large spike here is showing a lage number of missing values were replaced with the mean. 
2. **Distribution Shape:**
    - The distribution shape is suggesting that as the a large number of passengers were between (**20-40**) years. With a smaller count for (**0-10**) years, and (**60+**) years. 

##### Cabin: 

So, our cabin columns has categorical data which has cabin numbers in series. And, this column has the largest number of the missing values. For, a more better insight let's do a value count on it to have the idea how many cabins per series are assigned: 

![alt text](images/image%208.png)

So, here if we see the percentage, so it turns out to be that **77 percent** of the entries were missing/NA. So, i replaced them with **'Unknown'** values in the column. 

![alt text](images/image%2010.png)

##### Emarked:

Similarly, embarked column also has categorical data. And, for it there is a simple approach to replace it with **'unknown'**.

![alt text](images/image%2011.png)

## Visualization

As the dataset is cleaned. Let's proceed with cleaning of the dataset. Now, we will visualize it using **matplotlib.plt**:

- **Gender Distribution:** 

So, this is the distribution of all the genders we are seeign through the bar chart.

1. **More Males than Females:**  The male count (**577**) is significantely higher than the female count (**314**). Showing that the large proportion of passengers were male. In future visualization's you will see how it will affect the survival rates.

![alt text](images/image%2012.png)

2. **Gender Survvial:** The titanic evacuation followed a "women and childern first" policy. Since females were fewer in number, and being evcuated first there survival rate is higher as compared to males. 

![alt text](images/image%2013.png)

Now through bar chart the survived, and dead analysis based on males, and females:

![alt text](images/image%2014.png)

**2.1: Females Had a Higher Survival Rate:** A large number of females survived as there is significant **large pink bar**. A small blue bar as compared to males. Only a small number of males survived. This confirms the females, and children evacuation first policy.

**2.2: Males Has a Lower Survival Rate:** A small number of males survived as the **pink bar** is quite **small** compared to the females ones. Depicting a larger blue bar which shows dead case.

**2.3 Males vs Female Survival Ratio:**
- **79.9%** of survivors were female, while only **20.3%** were male. 
- This reinfornces the strong "women and children first" policy, as women had a higher chance of survival.

![alt text](images/image%2015.png)

**2.4 Males vs Female Not Survived Ratio:**
- **79.9%** of the non-survivors were male, while **24.1%** were female.
- The majority of males did not survive. 

![alt text](images/image%2016.png)

---

## Dataset Used
[Titanic Dataset (Kaggle)](https://www.kaggle.com/c/titanic/data)

The dataset consists of passenger details such as age, gender, ticket class, fare, and survival status.

- **`train.csv`** → Used for analysis & training (Contains `Survived` column)