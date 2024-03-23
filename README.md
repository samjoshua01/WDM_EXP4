<H1 ALIGN=CENTER> IMPLEMENTATION OF CLUSTER AND VISITOR SEGMENTATION FOR NAVIGATION PATTERNS  </H1>
<H3> NAME : Sam Joshua ML </H3>
<H3> REGISTER NUMBER : 212221040142</H3>
<H3>EXPERIMENT NO : 04 </H3>
<H3>DATE  : 23.03.2024 </H3>

## AIM: 
To implement Cluster and Visitor Segmentation for Navigation patterns in Python.
## DESCRIPTION:
<div align= "justify">Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website, 
  application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit. 
  This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts, 
  or services to meet the specific needs and preferences of each cluster.</div>
  
## PROCEDURE:
1) Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2) Define Age Groups by creating a dictionary containing age group conditions using Boolean conditions.
3) Segment Visitors by iterating through the dictionary and filter the visitors into respective age groups.
4) Visualize the result using matplotlib.

## PROGRAM:
```python
# read the data
import pandas as pd
visitor_df = pd.read_csv('/content/clustervisitor.csv')

# Perform segmentation based on characteristics (e.g., age groups)
age_groups = {
    'Young': visitor_df['Age'] <= 30,
    'Middle-aged': (visitor_df['Age'] > 30) & (visitor_df['Age'] <= 50),
    'Elderly': visitor_df['Age'] > 50
}

for group, condition in age_groups.items():  
    visitors_in_group = visitor_df[condition] 
    print(f"Visitors in {group} age group:")
    print(visitors_in_group)
```
## OUTPUT:
<img width="130" alt="image" src="https://github.com/Shrruthilaya-Gangadaran/WDM_EXP4/assets/93427705/fa2dd141-a3c8-4987-8784-a2e9ec7926c7">

## VISUALIZATION:
```python
# Create a list to store counts of visitors in each age group
visitor_counts=[]

# Count visitors in each age group
for group,condition in age_groups.items():
  visitors_in_group=visitor_df[condition]
  visitor_counts.append(len(visitors_in_group))
    
# Define age group labels and plot a bar chart
age_group_labels=list(age_groups.keys())
plt.figure(figsize=(8, 6))
plt.bar(age_group_labels, visitor_counts, color='skyblue')
plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()
```
## OUTPUT:
<img width="464" alt="image" src="https://github.com/Shrruthilaya-Gangadaran/WDM_EXP4/assets/93427705/cf4ff22a-2e6d-456b-926d-2fb1834a588b">

## RESULT:
Thus the cluster and visitor segmentation for navigation patterns was implemented successfully in python.
