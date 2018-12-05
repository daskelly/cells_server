# Installing `pagoda2`

In shell

```
yum install cairo-devel pango-devel libXt-devel openssl-devel gsl-devel boost-devel libcurl-devel
```

In `R`

```
library(devtools)
source("http://bioconductor.org/biocLite.R")
biocLite(c("GO.db", "org.Hs.eg.db","org.Mm.eg.db", "pcaMethods"), suppressUpdates=TRUE)
# comment out anaconda lines in ~/.bashrc first:
install_github("igraph/rigraph") # Don't install with install.packages()
install_github("jkrijthe/Rtsne", ref="openmp")
install.packages(c("Cairo", "urltools"))
install_github("hms-dbmi/pagoda2")
```
