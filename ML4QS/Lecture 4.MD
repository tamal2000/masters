# Cluster 

- Shortest path is not always the best option to use as a distance metric. Give an example. 
- Provide an dynamic time warping distance metric that avoids shortest path disadvantages. 
- Example of a subspace clustering would be better choice compare to the more common clustering approach. 



## At a Glance 
- Distance Metrics 
- Non-Hierarchical Clustering: 
- Hierarchical Clustering: 
- Subspace Clustering: 
- Data-stream Clustering: 
- Performance Evaluation: 

`Goal:` technique that can provide the insights in the data.  
`Individual data points:` finding cluster of data points for a given feature that represent different activities.   
`person:` a cluster for people who share similar characteristics. 

## Distance Metrics: 
Clustering alo generally work with a notion of distance between points. 
- Individual Data points distance metrics: 
	- Numerical data: 
		- Euclidean distance: distance between two points. 
		- Manhattan distance: points can be connected using horizontally or vertically not diagonally. 
		- Minkowski distance: a generalization of two metrics. Scaling is important to accommodate high magnitude and spread. 
	- Categorical data: 
		- convert to binary 
		- or similarity. 
- Person Level data metrics.  
	- Non-temporal distance metrics
		- mean, standard deviation, max, min of numerical data and binary conversion of categorical data. 
		- considering the distribution 
		- considering the stats like p-values
	- Temporal distance metrics: 
		- same granularity: 
			- raw-data base: raw series of data for each attribute. 1. differences between individual data points using euclidean distance. 2.  cross correlation like pearson correlation between the two different time series. 3. Dynamic time warping DTW, allows time series having different speed. 
			- feature-based: 
			- model-based: 