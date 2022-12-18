# GraB
## Abstract
We introduce GraB, a new class of datasets for community detection that exposes unique characteristics. As opposed to available datasets, our graphs are at the same time heterogeneous, i.e., include different types of nodes, comprise overlapping communities, i.e., nodes belong to multiple communities, and include attributes in the nodes. We show that state-of-the-art methods struggle in finding communities in such graphs, suggesting a gap in the field. 
<br>
The GraB datasets are real-world heterogeneuous graph sourced from the movie production domain, containing vertices of type movie, actor, writer, producer, editor, and director. 
The three variations (full/min/top 3) are different in the way that labels(genres) are assigned to person vertices. Details can be found in https://openreview.net/pdf?id=qsGpFRlK0a.
## Data format
The data is saved as sparce matricies in npz files, and can be loaded as follows:
```python
import numpy as np
import scipy.sparse as sp

data = np.load(pathToNpz)
loader = dict(data)
#adjacency matrix
adjacency = sp.csr_matrix((loader['adj_matrix.data'], loader['adj_matrix.indices'], loader['adj_matrix.indptr']), shape=loader['adj_matrix.shape'])

#attributes matrix
attributes = sp.csr_matrix((loader['attr_matrix.data'], loader['attr_matrix.indices'], loader['attr_matrix.indptr']), shape=loader['attr_matrix.shape'])

#label matrix
labels = sp.csr_matrix((loader['labels.data'], loader['labels.indices'], loader['labels.indptr']), shape=loader['labels.shape'])


```
# Citing
If you find GraB benchmask useful in your research, we ask that you cite the following paper:
```
@inproceedings{GraBBenchmark,
     author = {Knudsen, Malik S. and Brodal, Laurits A. and Peczalski, Peter K. and Moradan, Atefeh and Mottin, Davide and Assent, Ira},
     title = {GraB: Graph Benchmark for Heterogeneous Graph Clustering},
     abstract = {We introduce GraB, a benchmark for graph clustering that exposes unique characteristics. As opposed to available datasets, our graphs are at the same time heterogeneous, i.e., include different types of nodes and node attributes, and comprise overlapping clusters, i.e., each node belongs to multiple clusters. We empirically show the arduous characteristics of the datasets; the GraB datasets are available at https://anonymous.4open.science/r/GraB-benchmarks/.},
     year = {2022},
    }
```
