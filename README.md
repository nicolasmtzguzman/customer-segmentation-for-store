# Customer Segmentation for Store
## Introduction
The purpose of this project was to segment customers from a store based on various attributes such as
demographics and purchasing behavior in order to provide insights to help a marketing team craft personalized strategies to increase
sales and customer reactivation.

[Link to Data](https://www.kaggle.com/datasets/ahsan81/superstore-marketing-campaign-dataset/data)

Data Descriptions:

**Age**: the age of the customer

**Income**: customer's yearly household income

**TotalAmount**: total amount spent on all products in the last two years

**Recency**: number of days since the last purchase

**KidHome**: number of small children in customer's household

**Response**: 1 if customer accepted a membership offer in the last campaign, 0 otherwise

## Key Tasks
1. Data Cleaning
   - Handle Missing Values
   - Correct Data Types
2. Feature Engineering
   - Create Age and Total Amount Features
3. Exploratory Data Analysis
   - Heatmap
   - Data Distributions
   - Bivariate Analysis
4. Clustering Techniques
   - K-Means
   - DBSCAN
## Analysis
### K-Means on Age and Income
The first segmentation is based on Age and Income to identify customer segments that would give a positive response to a new membership.
![Screenshot 2024-08-16 130926](https://github.com/user-attachments/assets/a0c22357-0d8e-4865-9151-5f3ccc780e1d)
| Response  | 0 | 1 |
| -- | -- | -- |
| Cluster  |   |  |
| 0  | 0.789244  | 0.210756 |
| 1  | 0.877400  | 0.122600 |
| 2  | 0.899433  | 0.100567 |

The K-Means algorithm partitioned the data into 3 clusters, with the stars representing the centroids.
   - Cluster 0 would be the ideal group to target for the new membership, since they had the highest percentage of positive responses to the last membership
   - Clusters 1 and 2 could still be targeted for the new membership, but marketing campaigns should be refined to target those with lower incomes.

### K-Means on Recency and Total Amount
The next segmentation is based on Recency and Total Amount to identify customer segments that aren't shopping as much and come up with a possible marketing strategy.
![Screenshot 2024-08-16 133951](https://github.com/user-attachments/assets/a2831771-db32-45e7-835c-0ee22791664a)
| KidHome  | 0 | 1 | 2 |
| -- | -- | -- | -- |
| Cluster  |   |  |  |
| 0  | 0.326235  | 0.641397 | 0.032368|
| 1  | 0.938776  | 0.061224 | 0.000000|
| 2  | 0.855596  | 0.140794 | 0.003610|

After creating a cross-tabulation of the clusters with the amount of kids the customers have we see that:  
   - Cluster 1 shops the most and the majority of these customers don't have kids.
   - Cluster 0 shops the least and the majority of these customers have kids, so a possible marketing campaign is to offer deals on children products

### DBSCAN on Age and Income
Finally, we re-visit the segmentation based on Age and Income, but we run it on the DBSCAN Algorithm.
![Screenshot 2024-08-16 140507](https://github.com/user-attachments/assets/90ca0e8a-d7f0-43de-81a8-5944c890e0bc)
| Response  | 0 | 1 |
| -- | -- | -- |
| Cluster  |   |  |
| -1  | 424  | 288 |
| 0  | 1172  | 0 |
| 1  | 24  | 0 |
| 2  | 10  | 0 |
| 3  | 41  | 0 |
| 4  | 35  | 0 |
| 5  | 24  | 0 |
| 6  | 0  | 11 |
| 7  | 11  | 0 |
| 8  | 14  | 0 |
| 9  | 10  | 0 |
| 10  | 7  | 0 |






