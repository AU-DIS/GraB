# MoPed
## Abstract
We introduce MoPed, a new class of datasets for community detection that exposes unique characteristics. As opposed to available datasets, our graphs are at the same time heterogeneous, i.e., include different types of nodes, comprise overlapping communities, i.e., nodes belong to multiple communities, and include attributes in the nodes. We show that state-of-the-art methods struggle in finding communities in such graphs, suggesting a gap in the field. 
<br>
The MoPed datasets are real-world heterogeneuous graph sourced from the movie production domain, containing vertices of type movie, actor, writer, producer, editor, and director. 
The three variations (full/min/top 3) are different in the way that labels(genres) are assigned to person vertices. Details can be found in XXX.
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


