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
sudo yum install openssl-devel libcurl-devel libgit2-devel
sudo yum install gcc gcc-c++ make
sudo yum install libxml2-devel hdf5-devel
```

Uncomment Anaconda from `~/.bashrc`.
Installing `igraph` in R requires this.

From within R
```
if (!requireNamespace("BiocManager", quietly = TRUE))
    install.packages("BiocManager")
BiocManager::install("pcaMethods", version = "3.8")

library(devtools)
install_github("Novartis/hdf5r")
install_github("velocyto-team/velocyto.R")
```
