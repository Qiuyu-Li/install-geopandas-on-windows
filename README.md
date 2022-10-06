# install-geopandas-on-windows
Instructions on installing Geopandas on a Windows machine

#

I'm writing this article because it took me the whole afternoon to install Geopandas on my Windows machine and make it runnable. I know it's not likely to be the best solution, but it worked for me.

# STEPS

1. Download Miniconda, open the Powershell Prompt of Miniconda, create and activate a new environment.
2. `$conda install -y geopandas`

Then if you import geopandas at this point, it will likely to report:
```
OSError: could not find or load spatialindex_c-64.dll
```
So what you are gonna do is: 
```
$ conda uninstall rtree
$ conda install -c conda-forge rtree=0.9.3
```
Note that conda may still report errors after you've reinstalled an older version of rtree, because conda falsely looks outside its local environment and find another advanced version. I googled around for a while to find a way to change the PATH of conda, but ended in simply deleting the rtree I installed before in the "global" path. 
