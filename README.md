# Happiness and Well Being Analysis

## Project Overview
This project analysis the trend in happiness and well-being using a world happiness report data. While other approaches and techniques can be used for this project, I employed pandas and matplotlib for the purpose of accessing my studies on the aforementioned topics.

### [Data Source](https://www.kaggle.com/datasets/sazidthe1/global-happiness-scores-and-factors)
World Happiness Report: The [data](https://drive.google.com/file/d/1xCeoWcobQnKmms2UatMuvwjDC1Z3PAxP/view?usp=drive_link) was downloaded from kaggle.com

### Project Objective
My objective is to examine factors that influence happiness across different countries and regions, identify key drivers of well-being, and uncover patterns that highlight how various social, economic, and environmental factors contribute to overall happiness worldwide.

### Tools
The main tool used for this project is Acaconda installed through [anaconda](https://www.anaconda.com/download)
**The following python libraries were used:**
- Pandas
- Matplotlib

### Data Cleaning/preparation
In the initial data preparatory phase, I performed the following task
1. Data loading and inspection
2. Handling missing values and
3. Data cleaning and formatting

### Exploratory Data Analysis (EDA)
- EDA involves exploring the World Happiness Report data to answer key questions such as 
- What are the top 10 happiest and least happy countries?
- How does happiness score vary across regions?
- Is there a correlation between GDP per capita and happiness score?
- What is the distribution of social support across countries?
- How does healthy life expectancy impact happiness across regions?
- Which regions have the highest perceptions of corruption?
- Is there a link between generosity and happiness?
- How does the freedom to make life choices relate to happiness?
- What are the averages for each metric across regions?
- Which countries deviate the most from the regional average happiness score?

### Data Analysis
Include some interesting codes/features worked with
```python
# Importing the libraries 
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Importing the dataset by getting the path of the file
FilePath = r"C:\Users\GABRIEL\Downloads\WHR_2023.csv"

# Reading the dataset
df = pd.read_csv(FilePath)
df.head()

# Exploring the dataset
df.info()

# Top 10 happy countries
top_10_Happy = df.nlargest(10, 'happiness_score')
print(f"The top 10 happiest countries are: \n{top_10_Happy[['country', 'happiness_score']]}")

# Least 10 happy countries
least_10_Happy = df.nsmallest(10, 'happiness_score')
print(f"The least 10 happiest countries are: \n{least_10_Happy[['country', 'happiness_score']]}")

# Plotting on the top 10 happy countries on a column chart
top_10_Happy.plot(x='country', y= 'happiness_score', kind='bar', title='Ten Top Happiest Country', color='green')

#  Plot the least 10 happy countries on a column chart
least_10_Happy.plot(x='country', y= 'happiness_score', kind='bar', title='Ten Least Happy Countries', color='red')

