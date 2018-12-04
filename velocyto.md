# Installing velocyto

First install Anaconda

Then:
```
conda install numpy scipy cython numba matplotlib scikit-learn h5py click

pip install pysam
pip install velocyto
```

Install R and velocyto.R
```
sudo yum install R
```

From within R
```
library(devtools)
install_github("velocyto-team/velocyto.R")
```
