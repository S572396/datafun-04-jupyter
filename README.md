# datafun-04-jupyter

## Practice with Jupyter

create a project virtual environment in the .venv folder. 

```

py -m venv .venv
.venv\Scripts\Activate
py -m pip install -r requirements.txt

```

## Git add and commit 

```
git add .
git commit -m "first commit"
git push origin main

'''
## Download dependencies
'''
py -m pip install jupyterlab pandas matplotlib seaborn
py -m pip freeze > requirements.txt
'''
## Create Jupyter Notebook
'''
file add: sandraruiz_eda.ipynb
import libraries as abberviations:
import matplotlib.pyplot as plt
import pandas as pd
import seaborn as sns

'''

## Step 1: Load the Data
'''
df=sns.load_dataset('isis')
# inspect the data
print(df.head())

 # Step 2: Initial Data Inspection
 '''
  print (df.head(10))
  print (df.shape)
  print (df.dtypes)
  '''
  # Step 3:Initial Statistics displayed:
  '''
 print(df.describe())
 '''
 #Step 4: Initial Data Distribution for Numberical Columns
 '''
 df['sepal_length'].hist()

# Inspect histograms for all numberical columns
df.hist()

# Show all Plots
plt.show()
# Markdown notated of Results
'''
## step 5: Initial Data Distribution for categorical columns
'''
# Inspect value counts by categorical column
df['species'].value_counts()

# Inspect value counts by categorical columns
for col in df.select_dtypes(include=['object', 'category']).columns:
    # Display count plot
    sns.countplot(x=col, data=df)
    plt.title(f'Distribution of {col}')
    plt.show()  

# Markdown noted of 3 Species Resutls
'''
## Step 6: Initial Data Transformation and Feature Engineering
'''
# Rename a column
df.rename(columns={'sepal_length': 'Sepal_Length'}, inplace=True)

# Add a new column
df['Sepal_Area'] = df['Sepal_Length'] * df['sepal_width']

# Display histogram for 'Sepal_Length'
plt.hist(df['Sepal_Length']
plt.title('Histogram of Sepal Length')
plt.xlabel('Sepal Length')
plt.ylabel('Frequency')
plt.show()

# Markdown notated of sucessful rename of lowercase speal-length to uppercase Sepal_Length
'''

## Step 7 Initial Visualizations
#create chart types with seaborn and matplotlib
'''
sns.pairplot(df,hue='species')
plt.show()
#Markdown noted of graphs showing results displayed with new column Sepal_Area added in.

## Conclusion
'''
#A last display of all statistics summary displayed:
print(df.describe())
'''



