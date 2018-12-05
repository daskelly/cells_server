Problems with hdf5.
Version too old for `hdf5r` R package.

```
sudo yum remove hdf5-devel
conda install -c anaconda hdf5 
```

Finally, this worked:
```
curl -O https://mirrors.sorengard.com/cran/src/contrib/hdf5r_1.0.1.tar.gz
export LD_LIBRARY_PATH=$HOME/anaconda3/lib; R CMD INSTALL hdf5r_1.0.1.tar.gz
```

Add `export LD_LIBRARY_PATH=$HOME/anaconda3/lib` to `~/.bashrc`.
