# Hierarchical Clustering on Iris Data

Motivation, references, and the bulk of explanation of methods is (will eventually be) included in the report in the `report` directory, which contains both the .pdf and .docx files.

Only the .ipynb file has been uploaded (no .py version). Python code written in a Jupyter notebook (using Python 3.7.3). 

### Dependencies

Libraries that must be installed to run all code are: `matplotlib`, `numpy`, `scipy`, and `scikit-learn`, all of which can be installed with pip. If not already installed, this block of code can be pasted into a cell above the imports of the notebook:

```
!pip install numpy
!pip install matplotlib
!pip install scikit-learn
!pip install scipy
```

### Running the program

Assuming all necessary dependencies have been installed, run all cells to make sure all functions are available; all cells except for the last should run in under a minute, while the last cell will take around 2 minutes to run. Running all cells will additionally run three "playground" cells which give example usage of the functions discussed below.

The primary function of interest to run is `cluster_and_analyze` which will cluster the data based on the parameters as well as display the dendrogram and list the purity, Rand index, and normalized mutual information measures of the clustering. `cluster_and_analyze` takes the following parameters:
- `normalized`: boolean value, when `True` will normalize the data
- `distance_func`: function, should be one of the functions defined in the section `Cluster Similarity Functions` of the notebook
- `distance_metric`: function, should be one of the functions defined in the section `Distance Functions` of the notebook
- `use_weights`: 1D number array of length 4, optional, by default `[1,1,1,1]`, specifies the weights to use on the measures sepal length, sepal width, petal length, and petal width, in that order

The notebook also includes the varying of weights. There are two interesting functions to run in this section.

1. `greedy_optimize` runs a greedy "optimization" of the four weights, whose explanation can be found in the Methods section of the report. `greedy_optimize` takes the following parameters:
  - `clust_sim`: function, should be one of the functions defined in the section `Cluster Similarity Functions` of the notebook
  - `dist_metric`: function, should be one of the functions defined in the section `Distance Functions` of the notebook
  - `threshold`: float value, the stopping condition for the function based on the difference of cluster evaluation values between each iteration
  - `clust_eval`: function, should be one of the functions defined in the section `Cluster Evaluation Functions` of the notebook
  
2. `plot_weight_range` plots the cluster evaluation measures based on the parameters specified below:
  - `use_weights`: 1D number array of length 4, specifies the weights to use on the measures sepal length, sepal width, petal length, and petal width, in that order
  - `weight_index`: the index of `use_weights` to which `weight_range` will apply (making the value at this index defined in `use_weights` arbitrary)
  - `weight_range`: a list of values that specifies how the value of `use_weights` at the desired `weight_index` will vary. i.e. passing in `range(0,5)` will use 0, then 1, then 2, then 3, then 4 for `use_weights[weight_index]` during clustering
  - `clust_sim`: function, should be one of the functions defined in the section `Cluster Similarity Functions` of the notebook
  - `dist_metric`: function, should be one of the functions defined in the section `Distance Functions` of the notebook

### Library versions

Matplotlib: 3.3.2

Numpy: 1.16.4

SciPy: 1.2.1

SKLearn/SciKit-Learn: 0.21.2
