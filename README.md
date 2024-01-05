
# Strategic Aid Allocation for Global Development

Optimizing humanitarian aid allocation for HELP International by leveraging socio-economic and health indicators. Utilizing data analytics to identify countries in dire need for targeted assistance from a recent $10 million funding initiative.









## Project Description

This project endeavors to address the critical challenge of strategically and effectively allocating resources to countries in dire need of aid. HELP International, an international humanitarian NGO committed to fighting poverty and providing relief during disasters, has recently secured $10 million in funding. Now, the question arises: How can this money be utilized to bring about the most impactful and positive change?

As a data Scientist, my role is to leverage socio-economic and health factors to categorize countries based on their overall development status. By employing clustering techniques, we aim to identify and recommend priority countries that require immediate attention and aid. This data-driven initiative will provide valuable insights to HELP International's CEO, facilitating informed decision-making to maximize the impact of the allocated funds.

### Objective
- The objective of this project is to utilize data-driven methodologies to categorize countries based on socio-economic and health indicators. 
- the project aims to identify nations that are most in need of humanitarian aid.
- providing HELP International with strategic insights for effective allocation of funds and resources.

## Dataset
[Country-data.csv](https://github.com/SaurabhJaurat7030/Strategic-Aid-Allocation-for-Global-Development/files/13839165/Country-data.csv)

[data-dictionary.csv](https://github.com/SaurabhJaurat7030/Strategic-Aid-Allocation-for-Global-Development/files/13839172/data-dictionary.csv)

## Language and Libraries
Language : Python

Libraries
- Numpy
- Pandas
- Matplotlib
- Seaborn
- scipy
- Sklearn

## Project Approach.
1.  **Data Exploration**
- The dataset consists of 9 features, each capturing information on socio-economic and health indicators for various countries. like GPD, child mortaliry rate, income, health, imports etc. An initial exploration provides insights into the overall structure of the data.
- data info
  
  ![info](https://github.com/SaurabhJaurat7030/Strategic-Aid-Allocation-for-Global-Development/assets/154229876/60be3035-b74a-4a36-befa-55143fd5e79d)

2. **Data Preprocessing**
  - Data Description:
    
    ![Description](https://github.com/SaurabhJaurat7030/Strategic-Aid-Allocation-for-Global-Development/assets/154229876/73b3ef32-8396-42b5-bd87-caa588d7c1a6)
  - plotting Pairplot and Heatmap for checking the correlation 
![Pairflot_beforeLog](https://github.com/SaurabhJaurat7030/Strategic-Aid-Allocation-for-Global-Development/assets/154229876/993cb043-f2df-46e8-b3af-e4844b21d2e3)
![heatmap](https://github.com/SaurabhJaurat7030/Strategic-Aid-Allocation-for-Global-Development/assets/154229876/540eb6c8-7da8-4d40-8604-f0796eec1a5e)

  - after taking natural log of the feature and plotting the pairplot, many features show linear relationship

    ![pairplot_afterlog](https://github.com/SaurabhJaurat7030/Strategic-Aid-Allocation-for-Global-Development/assets/154229876/ca70938d-56a5-4e45-b71f-8a716032f48d)

  - Scaling the features by standard scaler
  - Checking for the outliers by plotting box plot then removing the outliers which lies below quantile of the 0.05 and above 0.95
    ![boxplot_lookingfor_outliers](https://github.com/SaurabhJaurat7030/Strategic-Aid-Allocation-for-Global-Development/assets/154229876/df4130a6-154e-437c-8855-4889db71e133)

  - Now lets reduce the dimensionality by principal component analysis with variance 94%

  ![no_of_comp_vs_variance](https://github.com/SaurabhJaurat7030/Strategic-Aid-Allocation-for-Global-Development/assets/154229876/dcbae8f0-b94a-469f-a5a0-f35dba40465d)

  ![PCA_dataframe](https://github.com/SaurabhJaurat7030/Strategic-Aid-Allocation-for-Global-Development/assets/154229876/0a3007be-e9a6-43ba-8b8b-130a8d430ed4)

3.  **Clustering Analysis**
- Checking if data frame can be cluster or not by hopkins statistics and score turns out above 0.72 so doing processing whith clutering
- Finding optimum numbers of cluster

  - silhouette_score
    
      ![silhoutte_score](https://github.com/SaurabhJaurat7030/Strategic-Aid-Allocation-for-Global-Development/assets/154229876/6a1720b6-2c8c-4baf-887e-5e461ab4e10e)
  - Sum of squared error
    
    ![SSE](https://github.com/SaurabhJaurat7030/Strategic-Aid-Allocation-for-Global-Development/assets/154229876/9c269372-2ad1-45d8-8220-ef4b4c97cdce)
  - Dendograph using methods as  Single, Complete, Average
    ![dendogram_complete](https://github.com/SaurabhJaurat7030/Strategic-Aid-Allocation-for-Global-Development/assets/154229876/2ae104c4-7f1a-4872-8c04-f289a69eda1b)
    ![dendogram](https://github.com/SaurabhJaurat7030/Strategic-Aid-Allocation-for-Global-Development/assets/154229876/53129416-8711-462d-88c7-d7e049845147)
    ![dendogram_avg](https://github.com/SaurabhJaurat7030/Strategic-Aid-Allocation-for-Global-Development/assets/154229876/4ce310ea-21ed-43e0-9a2d-929b28121275)

  - Decided to use 3 or 4 cluster
4. **Evaluation**
- Anslysis using 4 clusters using K-Means Clustering
  
  ![4_clust](https://github.com/SaurabhJaurat7030/Strategic-Aid-Allocation-for-Global-Development/assets/154229876/fc3db21b-d506-4a6f-8375-e1fe226c90b1)
![4_clust_lineplot](https://github.com/SaurabhJaurat7030/Strategic-Aid-Allocation-for-Global-Development/assets/154229876/93d63f9a-d202-43f0-b90c-9a970791931c)

Barplot for GDP vs clusters

![4_clust_GDP](https://github.com/SaurabhJaurat7030/Strategic-Aid-Allocation-for-Global-Development/assets/154229876/71fd2930-b0ff-42be-bb7c-e200ee361565)

Barplot for Child_mortality rate vs clusters

![4_clust_child_mort](https://github.com/SaurabhJaurat7030/Strategic-Aid-Allocation-for-Global-Development/assets/154229876/d2f12991-882b-40a9-a7c5-0306de718ce3)

Barplot for income vs clusters

![4_clust_income](https://github.com/SaurabhJaurat7030/Strategic-Aid-Allocation-for-Global-Development/assets/154229876/6a53213c-7351-4f34-aee8-78c3c17e5258)
  From this plot we can see that cluster 1 countries need financial aid

- Analsysis using 3 clusters

![3_clus](https://github.com/SaurabhJaurat7030/Strategic-Aid-Allocation-for-Global-Development/assets/154229876/f4a9be76-b2cd-4998-9e94-0903e7dfa4e1)
![3-clust_lineplot](https://github.com/SaurabhJaurat7030/Strategic-Aid-Allocation-for-Global-Development/assets/154229876/af2257f9-9538-4393-88d2-823ceafc5dd4)

4. **Insights and Recommendations**

Observation: Cluster #1 contains countries that are in direct need of financial aid, since:
It has disproportionately high child mortality rate, total_fer & inflation.
It has lowest gdpp, income & life_expectancy.
Cluster 1 has common countris

![final_income](https://github.com/SaurabhJaurat7030/Strategic-Aid-Allocation-for-Global-Development/assets/154229876/b6a4970d-6edb-4000-93c1-fb18e37e801f)
![final_child_mort](https://github.com/SaurabhJaurat7030/Strategic-Aid-Allocation-for-Global-Development/assets/154229876/eae15548-8cc0-411d-81e3-c51aa4c0bb66)
![final_GDP](https://github.com/SaurabhJaurat7030/Strategic-Aid-Allocation-for-Global-Development/assets/154229876/b93760e0-46de-4a0b-bbc6-ac6e79f79255)

**We can clearly see that countries are common in each of these dataframe with respect to (child_mort, income and gdpp).
Some of those countries are:**
- Congo, Dem. Rep.
- Sierra Leone
- Niger
- Mozambique
- Guinea-Bissau
- Central African Republic
- Liberia


