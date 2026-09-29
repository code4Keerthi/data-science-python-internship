# Week 3 – Clustering Analysis

## Project Overview

This project was completed as part of Week 3 of the Data Science with Python internship.

The objective of this week was to apply an unsupervised machine learning technique to the cleaned Adult Income Dataset and identify groups of observations with similar numerical characteristics.

K-Means clustering was used to group the observations based on selected numerical features. The appropriate number of clusters was evaluated using the Elbow Method and Silhouette Score.

## Dataset

The dataset used for this project is the Adult Income Dataset, also known as the Census Income Dataset.

The cleaned dataset contains:

- 45,175 observations
- 15 variables
- No missing values
- No duplicate rows

The cleaned dataset was prepared during Week 1 and was also used for the exploratory analysis completed during Week 2.

## Objectives

The main objectives of this project were:

- To apply an unsupervised machine learning technique to the cleaned dataset.
- To select appropriate numerical features for clustering.
- To standardize the selected features before clustering.
- To evaluate different numbers of clusters using the Elbow Method.
- To evaluate clustering quality using the Silhouette Score.
- To select a suitable number of clusters.
- To train a final K-Means clustering model using the complete dataset.
- To analyze the characteristics of the resulting clusters.
- To examine income distributions across the resulting clusters as a post-clustering analysis.
- To document the methodology, results, challenges, and limitations.

## Features Used for Clustering

Six numerical features were selected:

- `age`
- `fnlwgt`
- `education-num`
- `capital-gain`
- `capital-loss`
- `hours-per-week`

The `income` variable was not used as an input feature during clustering. It was examined only after the clusters were created to understand the composition of the resulting groups.

## Methodology

The clustering workflow consisted of the following steps:

1. Load the cleaned Adult Income Dataset.
2. Select six numerical features.
3. Standardize the selected features using `StandardScaler`.
4. Test K-Means models for K values from 2 through 10.
5. Evaluate the models using the Elbow Method.
6. Calculate Silhouette Scores using a reproducible sample of 10,000 observations.
7. Select K = 2 based primarily on the highest Silhouette Score.
8. Train the final K-Means model on the complete standardized dataset.
9. Analyze the resulting cluster profiles.
10. Examine income distributions across the clusters.

## Model Selection

The Elbow Method showed a substantial reduction in inertia as the number of clusters increased, with the reduction becoming less pronounced around K = 4 to K = 5.

The Silhouette Score was calculated for K values from 2 through 10 using a reproducible sample of 10,000 observations.

The highest Silhouette Score was obtained for:

- **K = 2**
- **Silhouette Score ≈ 0.5111**

Based primarily on the Silhouette Score, K = 2 was selected for the final K-Means model.

## Final Clustering Model

The final K-Means model was trained using:

- Number of clusters: 2
- `random_state`: 42
- `n_init`: 10
- Training observations: 45,175
- Numerical features: 6

The resulting cluster distribution was:

| Cluster | Observations | Percentage |
|---|---:|---:|
| Cluster 0 | 2,098 | 4.64% |
| Cluster 1 | 43,077 | 95.36% |

The clusters were therefore highly unequal in size.

## Cluster Analysis

The cluster profiles were analyzed using the average values of the six numerical features.

The most noticeable difference between the clusters was observed in `capital-loss`.

Other differences included:

- Cluster 0 had a higher average age.
- Cluster 0 had a higher average education-num.
- Cluster 0 had a higher average hours-per-week.
- The average `fnlwgt` values were relatively similar between the clusters.

## Post-Clustering Income Analysis

The `income` variable was not used during the clustering process.

After the clusters were created, income distributions were examined to provide an additional descriptive interpretation.

The income distribution within each cluster was:

| Cluster | <=50K | >50K |
|---|---:|---:|
| Cluster 0 | 47.76% | 52.24% |
| Cluster 1 | 76.54% | 23.46% |

These results describe the composition of the resulting clusters and should not be interpreted as an income prediction or classification result.

## Visualizations

The following visualizations were created:

- `elbow_method.png`
- `silhouette_score.png`
- `cluster_profile_comparison.png`
- `income_distribution_across_clusters.png`

### Elbow Method

Shows the change in K-Means inertia for different numbers of clusters.

### Silhouette Score

Shows the Silhouette Score for K values from 2 through 10.

### Cluster Profile Comparison

Compares the standardized average feature values of the resulting clusters.

### Income Distribution Across Clusters

Shows the percentage distribution of income categories within each cluster.

## Computational Consideration

The initial attempt to calculate the Silhouette Score using all 45,175 observations required substantial computation time.

To make the evaluation practical, a reproducible sample of 10,000 observations was used for Silhouette Score calculation.

A fixed random state of 42 was used to ensure that the same sample could be reproduced.

The final K-Means model was still trained on the complete dataset of 45,175 observations.

## Model File

The trained K-Means model was saved using Joblib:

```text
models/kmeans_clustering_model.pkl