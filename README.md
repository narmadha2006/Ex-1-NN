<H3>ENTER YOUR NAME</H3> NARMADHA S
<H3>ENTER YOUR REGISTER NO.</H3> 212223220065
<H3>EX. NO.1</H3>
<H3>DATE</H3> 15-03-2025
<H1 ALIGN =CENTER> Introduction to Kaggle and Data preprocessing</H1>

## AIM:

To perform Data preprocessing in a data set downloaded from Kaggle

## EQUIPMENTS REQUIRED:
Hardware – PCs
Anaconda – Python 3.7 Installation / Google Colab /Jupiter Notebook

## RELATED THEORETICAL CONCEPT:

**Kaggle :**
Kaggle, a subsidiary of Google LLC, is an online community of data scientists and machine learning practitioners. Kaggle allows users to find and publish data sets, explore and build models in a web-based data-science environment, work with other data scientists and machine learning engineers, and enter competitions to solve data science challenges.

**Data Preprocessing:**

Pre-processing refers to the transformations applied to our data before feeding it to the algorithm. Data Preprocessing is a technique that is used to convert the raw data into a clean data set. In other words, whenever the data is gathered from different sources it is collected in raw format which is not feasible for the analysis.
Data Preprocessing is the process of making data suitable for use while training a machine learning model. The dataset initially provided for training might not be in a ready-to-use state, for e.g. it might not be formatted properly, or may contain missing or null values.Solving all these problems using various methods is called Data Preprocessing, using a properly processed dataset while training will not only make life easier for you but also increase the efficiency and accuracy of your model.

**Need of Data Preprocessing :**

For achieving better results from the applied model in Machine Learning projects the format of the data has to be in a proper manner. Some specified Machine Learning model needs information in a specified format, for example, Random Forest algorithm does not support null values, therefore to execute random forest algorithm null values have to be managed from the original raw data set.
Another aspect is that the data set should be formatted in such a way that more than one Machine Learning and Deep Learning algorithm are executed in one data set, and best out of them is chosen.


## ALGORITHM:
STEP 1:Importing the libraries<BR>
STEP 2:Importing the dataset<BR>
STEP 3:Taking care of missing data<BR>
STEP 4:Encoding categorical data<BR>
STEP 5:Normalizing the data<BR>
STEP 6:Splitting the data into test and train<BR>

##  PROGRAM:


# Import Libraries
import pandas as pd
from sklearn.preprocessing import MinMaxScaler
from sklearn.model_selection import train_test_split

# Read the dataset
df = pd.read_csv("/content/sample_data/Churn_Modelling.csv")

# Handling Missing Values
print("Missing Values:\n", df.isnull().sum(), "\n")

# Handle duplicates (if any)
duplicates = df.duplicated().sum()
print(f"Number of duplicate rows: {duplicates}\n")

# Check for Outliers using describe()
print("Outliers (Summary Statistics):\n", df.describe(), "\n")

# Drop unnecessary columns (like 'Surname', 'Geography', and 'Gender')
df = df.drop(['Surname', 'Geography', 'Gender'], axis=1)

# Normalize the dataset using MinMaxScaler
scaler = MinMaxScaler()
df_normalized = pd.DataFrame(scaler.fit_transform(df.drop('Exited', axis=1)), columns=df.columns[:-1])

# Normalized dataset
print("Normalized dataset:\n", df_normalized.head(), "\n")

# Define features (X) and target (y)
X = df_normalized.values
y = df['Exited'].values

# Input & Output Values
print("Input Values (Features):\n", X[:5])  # Show first 5 rows of features
print("\nOutput Values (Target):\n", y[:5])  # Show first 5 values of target

# Split the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Splitting the data for training & testing
print(f"\nTraining data size: {len(X_train)}")
print(f"Testing data size: {len(X_test)}")



## OUTPUT:


MISSING VALUES:


![image](https://github.com/user-attachments/assets/f7869dff-df93-4772-ad35-ebbbc4652475)


OUTLIERS:


![image](https://github.com/user-attachments/assets/cb4360eb-c58e-4d15-8c2c-45d607dc99d7)


NORMALIZED DATASET:


![image](https://github.com/user-attachments/assets/e833488e-f0e3-42d7-8ae1-9d5e6e55e449)


INPUT & OUTPUT VALUES:


![image](https://github.com/user-attachments/assets/493e20f5-bb38-43b8-bfaf-018d224eee85)
![image](https://github.com/user-attachments/assets/4eb2551e-0afc-4e67-847a-923cdea9e6b3)



SPILTING THE DATA FOR TRAINING AND TESTING:


![image](https://github.com/user-attachments/assets/fca2429a-bcdd-41fb-8333-693cc707e7df)








## RESULT:
Thus, Implementation of Data Preprocessing is done in python  using a data set downloaded from Kaggle.


