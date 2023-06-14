## DendroX-Util

Packages to create JSON input for the DendroX app.

Code for demonstration can be found in the demo folder.

### Python
To install the package:
```
pip install dendrox
```
To use the package:
```
from dendrox import get_json
import seaborn

g = seaborn.clustermap(...)
get_json(g) # will create an input json file for the row dendrogram
```
Interface:
```
def get_json(g, row=True, labels=None, fname='nodes'):
    # g: output object from seaborn.clustermap function
    # row: whether to get json data of the row dendrogram or the column dendrogram
    # labels: text labels in the order as in the input data to the clustermap 
    #         function. If left to None, it will extract labels from the input 
    #         g object.
    # fname: the file name of the output json file
    ...
```
### R
To install the package, do the following:
```
install.packages(reticulate)
reticulate::install_miniconda()
reticulate::py_install('dendrox',pip=T)
install.packages(dendrox)
```
To use the package:
```
library(pheatmap)
library(dendrox)

g = pheatmap(...)
get_json(g) # will create an input json file for the row dendrogram
```
Interface:
````
get_json <- function(g,row=T,labels=NA, fname='nodes'){
    # g: output object from pheatmap function
    # row: whether to get json data of the row dendrogram or the column dendrogram
    # labels: text labels in the order as in the input data to pheatmap. If left 
    #         NA, it will extract labels from the input g object.
    # fname: the file name of the output json file
    ...
}
```