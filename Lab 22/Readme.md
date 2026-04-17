Clustering World Economies with K-Means & PCA
Objective

To identify meaningful patterns in global economic development by applying unsupervised machine learning techniques to World Bank indicators and evaluating how well data-driven clusters align with established income classifications.

Methodology
Collected 10 key development indicators for approximately 160 countries using the World Bank API (wbgapi)
Preprocessed data by standardizing all features using StandardScaler to ensure equal weighting across variables
Applied K-Means clustering to segment countries into distinct economic groups
Evaluated optimal cluster count (K) using both the Elbow Method and Silhouette Analysis across K = 2 to K = 10
Reduced dimensionality using Principal Component Analysis (PCA) to visualize clusters in a 2D space
Compared algorithmically generated clusters with World Bank income classifications using cross-tabulation
Replicated the clustering pipeline on California Housing data to validate generalizability of the approach
Key Findings
The optimal number of clusters was K = [FILL IN], based on a balance between inertia reduction and silhouette score stability
Clusters showed [strong/moderate/weak] alignment with World Bank income groups, indicating that development indicators capture meaningful economic structure but do not fully replicate official classifications
Higher-income countries tended to cluster together due to similarities in indicators such as GDP per capita, infrastructure, and education, while lower-income countries formed distinct groups characterized by different development constraints
PCA visualization confirmed clear separation between major economic clusters, with some overlap suggesting transitional or mixed-development economies
The methodology successfully generalized to a different dataset (California Housing), demonstrating the robustness of clustering pipelines across domains
