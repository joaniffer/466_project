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

Assuming all necessary dependencies have been installed, run all cells to make sure all functions are available; this should take less than a minute. Running all cells will additionally run the last cell, which is the only cell in the `Playground` section of the notebook. This cell may be modified or deleted. If you intend to compare the separate outputs, it's recommended to create additional cells.

The function of interest to run is `cluster_and_analyze` which will cluster the data based on the parameters as well as display the dendrogram and list the purity, Rand index, and normalized mutual information measures of the clustering. `cluster_and_analyze` takes the following parameters:
- `normalized`: boolean value, when `True` will normalize the data
- `distance_func`: function, should be one of the functions defined in the section `Cluster Similarity Functions` of the notebook
- `distance_metric`: function, should be one of the functions defined in the section `Distance Functions` of the notebook
- `use_weights`: 1D number array of length 4, optional, by default `[1,1,1,1]`, specifies the weights to use on the measures sepal length, sepal width, petal length, and petal width, in that order

### Library versions

Matplotlib: 3.3.2

Numpy: 1.16.4

SciPy: 1.2.1

SKLearn/SciKit-Learn: 0.21.2
