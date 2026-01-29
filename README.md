# Spotify Audio Features Cluster Analysis
## Note: 
This project was originally developed around Jun,2026 and pushed later for portfolio consolidation.
The dataset used for processing was the historical one, and the recent changes in the Spotify API Terms and Conditions no longer permit usage of this kind!

## Overview
This notebook performs a cluster analysis on Nepalese Spotify songs based on their audio features. The goal is to identify distinct musical groups within the dataset and understand their unique characteristics. By clustering songs, we can gain insights into different music styles and their underlying acoustic properties.

## Data
The dataset used in this analysis (`spotify_2340.csv`) contains various audio features for Nepalese Spotify songs, such as BPM, Energy, Danceability, Loudness, Valence, Acousticness, and Popularity. The data was preprocessed to handle missing values and scale numerical features before clustering.

## Methodology
1.  **Data Loading and Preprocessing**: The CSV file was loaded into a pandas DataFrame. Missing values were dropped, and irrelevant columns ('A.Sep') were removed. Numerical features were then scaled using `StandardScaler` to ensure that all features contribute equally to the clustering process.
2.  **Feature Selection**: Only numerical audio features were selected for clustering.
3.  **Determining Optimal Clusters**: The Elbow method and Silhouette score were used to determine the optimal number of clusters (k) for KMeans. Both methods suggested 4 clusters.
4.  **K-Means Clustering**: K-Means algorithm was applied with `n_clusters=4` to group the songs based on their scaled audio features.
5.  **Cluster Profiling**: The mean values of the original (unscaled) features were calculated for each cluster to understand their distinct characteristics.
6.  **Top Tracks Analysis**: The top popular tracks within each cluster and the tracks closest to the cluster centers were identified to provide concrete examples of songs representing each cluster.

## Results
Four distinct clusters were identified, each representing a unique musical profile:

-   **Cluster 0 (Acoustic & Mellow)**: Songs with lower energy, danceability, and loudness but higher acousticness. These tracks are generally more serene and less intense.
    -   *Representative track (closest to center)*: 'Banideu' by Garage Music
-   **Cluster 1 (Energetic & Up-tempo)**: Songs characterized by higher BPM and energy, with moderate danceability and lower acousticness. These tend to be more dynamic and driving.
    -   *Representative track (closest to center)*: 'Jaba Din' by Sugam Pokharel
-   **Cluster 2 (Mid-Tempo & Balanced)**: Tracks with the lowest BPM, moderate energy, good danceability, and higher acousticness. These songs offer a balanced listening experience.
    -   *Representative track (closest to center)*: 'Bagaichama Najau Timi' by Udit Narayan
-   **Cluster 3 (Upbeat & Danceable)**: Songs exhibiting high danceability, high energy, and high valence, suggesting upbeat and positive-sounding tracks. Acousticness is lower.
    -   *Representative track (closest to center)*: 'Bhanekai Thiye' by Yash Kumar

This analysis provides a clear understanding of the diverse musical landscape within the Nepalese Spotify dataset, categorizing songs into meaningful groups based on their intrinsic audio characteristics.
