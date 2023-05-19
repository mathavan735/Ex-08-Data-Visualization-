# Ex-08-Data-Visualization-

## AIM
To Perform Data Visualization on the given dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


# CODE
```
Developed by:Mathavan S
Reg no:212221220031
# Importing packages
import pandas as pd
import numpy as np

# Importing visualization libraries
import seaborn as sns
import matplotlib.pyplot as plt

df_super = pd.read_csv('Superstore.csv')

df_super.head(5)

df_super=df_super.groupby(by=["Category"]).sum()
labels=[]
for i in df_super.index:
    labels.append(i)  
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.pie(df_super["Profit"],colors = colors,labels=labels, autopct = '%0.0f%%')
plt.show()


sns.set_style('whitegrid')
sns.countplot(x='Segment',data=df_super, palette='rainbow')

sns.set_style('whitegrid')
sns.countplot(x='Category',data=df_super, palette='rainbow')

sns.set_style('whitegrid')
sns.countplot(x='Sub-Category',data=df_super, palette='rainbow')

sns.set_style('whitegrid')
sns.countplot(x='Region',data=df_super, palette='rainbow')

sns.set_style('whitegrid')
sns.countplot(x='Ship Mode',data=df_super, palette='rainbow')

category_hist = sns.FacetGrid(df_super, col='Ship Mode', palette='rainbow')
category_hist.map(plt.hist, 'Category')
category_hist.set_ylabels('Number')

subcategory_hist = sns.FacetGrid(df_super, col='Segment', height=10.5, aspect=4.6)
subcategory_hist.map(plt.hist, 'Sub-Category')
subcategory_hist.set_ylabels('Number')

grid = sns.FacetGrid(df_super, row='Category', col='Sub-Category', height=2.2, aspect=1.6)
grid.map(sns.barplot, 'Profit', 'Segment', alpha=.5, ci=None)
grid.add_legend()
```

# OUPUT:

![1](https://github.com/LavanyaSIT/Ex-08-Data-Visualization-/assets/130207418/7
![2](https://github.com/LavanyaSIT/Ex-08-Data-Visualization-/assets/130207418/730506a4-7572-4dc9-9693-f00a08c44384)
![3](https://github.com/LavanyaSIT/Ex-08-Data-Visualization-/assets/130207418/de36f8ac-1d87-45ac-9399-d9a7b9b8297e)
4![4](https://github.com/LavanyaSIT/Ex-08-Data-Visualization-/assets/130207418/3aae8c62-e488-4fee-8a73-164d414b95e6)

![5](https://github.com/LavanyaSIT/Ex-08-Data-Visualization-/assets/130207418/db7816b1-b264-4a9d-bbb2-45844f71cd9a)
![6](https://github.com/LavanyaSIT/Ex-08-Data-Visualization-/assets/130207418/64511339-0310-4c78-8d34-8efa908e81cd)
![7](https://github.com/LavanyaSIT/Ex-08-Data-Visualization-/assets/130207418/b82be996-ab21-46d1-b473-ceed5f38e721)
![9](https://github.com/LavanyaSIT/Ex-08-Data-Visualization-/assets/130207418/3ced38e6-9229-4ba6-b83a-8e95bf1035bf)
![10](https://github.com/LavanyaSIT/Ex-08-Data-Visualization-/assets/130207418/42c4fe85-a368-4ff0-8fcf-d995446d9592)

#RESULT:
Data Visualization has been performed on a complex dataset and saved the data to a file.
