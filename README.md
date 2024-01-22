# machine_learning_project-unsupervised-learning

## Project Outcomes
- Unsupervised Learning: perform unsupervised learning techniques on a wholesale data dataset. The project involves four main parts: exploratory data analysis and pre-processing, KMeans clustering, hierarchical clustering, and PCA.
### Duration:
Approximately 1 hour and 40 minutes
### Project Description:
In this project, we will apply unsupervised learning techniques to a real-world data set and use data visualization tools to communicate the insights gained from the analysis.

The data set for this project is the "Wholesale Data" dataset containing information about various products sold by a grocery store.
The project will involve the following tasks:

-	Exploratory data analysis and pre-processing: We will import and clean the data sets, analyze and visualize the relationships between the different variables, handle missing values and outliers, and perform feature engineering as needed.
-	Unsupervised learning: We will use the Wholesale Data dataset to perform k-means clustering, hierarchical clustering, and principal component analysis (PCA) to identify patterns and group similar data points together. We will determine the optimal number of clusters and communicate the insights gained through data visualization.

The ultimate goal of the project is to gain insights from the data sets and communicate these insights to stakeholders using appropriate visualizations and metrics to make informed decisions based on the business questions asked."

### Glossary
reference: https://archive.ics.uci.edu/dataset/292/wholesale+customers
1)	FRESH: annual spending (m.u.) on fresh products (Continuous);
2)	MILK: annual spending (m.u.) on milk products (Continuous);
3)	GROCERY: annual spending (m.u.)on grocery products (Continuous);
4)	FROZEN: annual spending (m.u.)on frozen products (Continuous)
5)	DETERGENTS_PAPER: annual spending (m.u.) on detergents and paper products (Continuous) 
6)	DELICATESSEN: annual spending (m.u.)on and delicatessen products (Continuous); 
7)	CHANNEL: Horeca (Hotel/Restaurant/Cafe) [value 1] or Retail channel [value 2] (Nominal)
8)	REGION: Lisbon [value 1], Oporto [value 2] or Other [value 3] (Nominal)

### List of Figures
Figure 1.0: "Histogram of Fresh before outliers removed"

Figure 1.1: "Box Plot of Fresh before outliers removed"

Figure 1.2: "Histogram of Milk before outliers removed"

Figure 1.3: "Box Plot of Milk before outliers removed"
Figure 1.4: "Histogram of Grocery before outliers removed"

Figure 1.5: "Box Plot of Grocery before outliers removed"

Figure 1.6: "Histogram of Frozen before outliers removed"

Figure 1.7: "Box Plot of Frozen before outliers removed"

Figure 1.8: "Histogram of Detergents_Paper before outliers removed"

Figure 1.9: "Box Plot of Detergents_Paper before outliers removed"

Figure 1.10: "Histogram of Delicassen before outliers removed"

Figure 1.11: "Box Plot of Delicassen before outliers removed"

Figure 2.0: "Frequency of Channel categories before outliers removed"

Figure 2.1: "Frequency of Region categories before outliers removed"

Figure 3.0: "Scatter Plot of Fresh vs Milk before outliers removed"

Figure 3.1: "Scatter Plot of Fresh vs Grocery before outliers removed"

Figure 3.2: "Scatter Plot of Fresh vs Frozen before outliers removed"

Figure 3.3: "Scatter Plot of Fresh vs Detergents_Paper before outliers removed"

Figure 3.4: "Scatter Plot of Fresh vs Delicassen before outliers removed"

Figure 3.5: "Scatter Plot of Milk vs Grocery before outliers removed"

Figure 3.6: "Scatter Plot of Milk vs Frozen before outliers removed"

Figure 3.7: "Scatter Plot of Milk vs Detergents_Paper before outliers removed"

Figure 3.8: "Scatter Plot of Milk vs Delicassen before outliers removed"

Figure 3.9: "Scatter Plot of Grocery vs Frozen before outliers removed"

Figure 3.10: "Scatter Plot of Grocery vs Detergents_Paper before outliers removed"

Figure 3.11: "Scatter Plot of Grocery vs Delicassen before outliers removed"

Figure 3.12: "Scatter Plot of Frozen vs Detergents_Paper before outliers removed"

Figure 3.13: "Scatter Plot of Frozen vs Delicassen before outliers removed"

Figure 3.14: "Scatter Plot of Detergents_Paper vs Delicassen before outliers removed"

Figure 4.0: "Scatter Plot of Fresh vs Milk after outliers removed"

Figure 4.1: "Scatter Plot of Fresh vs Grocery after outliers removed"

Figure 4.2: "Scatter Plot of Fresh vs Frozen after outliers removed"

Figure 4.3: "Scatter Plot of Fresh vs Detergents_Paper after outliers removed"

Figure 4.4: "Scatter Plot of Fresh vs Delicassen after outliers removed"

Figure 4.5: "Scatter Plot of Milk vs Grocery after outliers removed"

Figure 4.6: "Scatter Plot of Milk vs Frozen after outliers removed"

Figure 4.7: "Scatter Plot of Milk vs Detergents_Paper after outliers removed"

Figure 4.8: "Scatter Plot of Milk vs Delicassen after outliers removed"

Figure 4.9: "Scatter Plot of Grocery vs Frozen after outliers removed"

Figure 4.10: "Scatter Plot of Grocery vs Detergents_Paper after outliers removed"

Figure 4.11: "Scatter Plot of Grocery vs Delicassen after outliers removed"

Figure 4.12: "Scatter Plot of Frozen vs Detergents_Paper after outliers removed"

Figure 4.13: "Scatter Plot of Frozen vs Delicassen after outliers removed"

Figure 4.14: "Scatter Plot of Detergents_Paper vs Delicassen after outliers removed"

Figure 5: Correlation Heatmap

Figure 6: Elbow Method chart

Figure 7: Silhouette Analysis chart

Figure 8: Dendrogram of Hierarchical clustering ward method chart

Figure 9: PCA explained variance chart

## Project

### Part 1: EDA
![Figure 1](visualizations\figure_1_histograms_boxplots_of_quantitative_variables_before_outliers_removed.png)

With the exception of the categorical variables, all quantitative variables had a skewed distribution to the right.


![Figure 3](visualizations\figure_3_scatter_plots_of_column_pairs_before_outliers_removed.png)

It is clear that not many of the variables are correlated


![Figure 4](visualizations\figure_4_scatter_plots_of_column_pairs_after_outliers_removed.png)

![correlation_matrix_difference](images\correlation_diff.png)

After removing 108 records containing outliers, the absolute difference between the correlations did not change much, other than the correlation between "Delicassen" and "Frozen".


![Figure 5](visualizations\figure_5_correlation_heatmap.png)

The only columns showing a strong correlation are 'grocery' and 'detergents_paper'; 'grocery' and 'milk'. Therefore, 'grocery' will be dropped.


#### Data Transformation

the Standard scaler was used to transform the quantitative values


#### Feature Selection

After applying a variance threshold of 0.1, no quantiative columns passed the threshold and all were fit to be included in the model

The categorical variables and 'grocery' were dropped.

No PCA was performed as it was included near the end of this project, but would have been done here at this stage going into the model.


### Part 2: KMeans Clustering
![Figure 6](visualizations\figure_6_elbow_method_chart.png)
![Figure 7](visualizations\figure_7_silhouette_analysis_chart.png)

Both charts lead to a optimal number of clusters of 4.  The model achieved convergence and the cluster assignment is as follows:
![kmeans output](images\kmeans.png)

### Part 3: Hierarchical Clustering
![Figure 8](visualizations\figure_8_dendrogram_of_Hierarchical_clustering_ward_method_chart.png)

From the dendrogram, I chose the t value of 16 for the AgglomerativeClustering model.  This also had a number of clusters of 4, same as kmeans.


### Part 4: PCA
![Figure 9](visualizations\Figure_9__PCA_explained_variance_chart.png)

If I were to do the model again, I would chose to either use only 3 (containing 81% of explained variance) or 4 (containing 94% of explained variance) principle components as model features.


