---
title: Creating a virtual environment with Anaconda
date: 2020-07-15 14:41:57 Z
categories:
- machine-learning
tags:
- machine learning [ML]
- Data Science [DS]
- Anaconda
- Python
- Jupyter
- scikit-learn
layout: post
comments: true
description: Installation and launching jupyter notebook with selected conda environment in Windows 10
author: Rasik Kane
---

# Anaconda
Anaconda comes with Conda and Anaconda navigator. Conda is an open source package management system and environment management system that runs on Windows, macOS and Linux. Conda helps to find and isntall packages.


## Download anaconda installer and install anaconda
* Latest Anaconda installers are available for [download](https://www.anaconda.com/products/individual)


## List of packages
* [Anaconda package list](https://docs.anaconda.com/anaconda/packages/pkg-docs/) is available for users to review
* From DS and ML point of view, considering a latest conda version for 64-bit Windows with Python 3.7:
  * **Installer Built in packages**: [async_generator](https://github.com/python-trio/async_generator), [beautifulsoup4](http://www.crummy.com/software/BeautifulSoup/), [bkcharts](http://github.com/bokeh/bkcharts), [bokeh](http://bokeh.pydata.org/), [curl](http://curl.haxx.se/), [cython](http://www.cython.org/), [dask](https://dask.org/), [flask](http://flask.pocoo.org/), [hdf5](http://www.hdfgroup.org/HDF5/), [ipython](https://ipython.org/), [jedi](https://github.com/davidhalter/jedi/), [jupyter](http://jupyter.org/), [matplotlib](http://matplotlib.org/), [networkx](https://networkx.github.io/), [nltk](http://nltk.org/), [numpy](http://numpy.scipy.org/), [pandas](http://pandas.pydata.org/), [pathlib2](https://github.com/mcmtroffaes/pathlib2), [pep8](http://pep8.readthedocs.org/), [pytest](https://docs.pytest.org/en/latest/), [regex](https://bitbucket.org/mrabarnett/mrab-regex), [scipy](http://www.scipy.org/), [sqlalchemy](http://www.sqlalchemy.org/),  [tqdm](https://pypi.python.org/pypi/tqdm)
  * **Available packages**: [arrow](https://github.com/crsmithdev/arrow), [azure](https://github.com/Azure/azure-sdk-for-python), [blaze](http://blaze.pydata.org/), [chainer](https://chainer.org/), [coverage](https://coverage.readthedocs.io/), [cudnn](https://docs.anaconda.com/anaconda/packages/py3.7_win-64/None), [dask-ml](http://github.com/dask/dask-ml), [django](http://www.djangoproject.com/), [elasticsearch](https://github.com/elastic/elasticsearch-py), [fastparquet](http://github.com/dask/fastparquet), [git](https://git-scm.com/), [graphviz](http://www.graphviz.org/), [mysql](https://www.mysql.com/), [nginx](http://www.nginx.org/), [nodejs](https://nodejs.org/), [opencv](http://opencv.org/), [plotly](https://plot.ly/python/), [pyspark](http://spark.apache.org/), [pytorch](http://pytorch.org/), [pytorch-gpu](https://docs.anaconda.com/anaconda/packages/py3.7_win-64/None), [scikit-learn](http://scikit-learn.org/), [seaborn](https://seaborn.pydata.org/), [torchvision](http://pytorch.org/), [tensorflow](http://tensorflow.org/), [tensorflow-gpu](http://tensorflow.org/), [teradata](http://github.com/teradata/PyTd), [virtualenv](https://virtualenv.pypa.io/)


## Creating conda environment
* Anaconda guide for creating a python virtual environment can be found [here](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html)
* Once acustomed with conda, users can refer to [cheet sheet](https://conda.io/projects/conda/en/latest/_downloads/843d9e0198f2a193a3484886fa28163c/conda-cheatsheet.pdf) for quick reference.


## Example For creating conda environment with pytorch on windows 10
### Create conda venv
#### I want to create **virtual environment by name *'torch'***, as I wish to install pytorch. Type following command in command prompt.
```
C:\Users\rasik>conda create --name torch
```
#### conda asks for permission to proceed
```
## Package Plan ##
  environment location: C:\Users\rasik\Anaconda3\envs\torch
Proceed ([y]/n)? y
```
#### On successful creation, conda prompts user to activate new environment
```
Preparing transaction: done
Verifying transaction: done
Executing transaction: done
# To activate this environment, use
#     $ conda activate torch
# To deactivate an active environment, use
#     $ conda deactivate
```
#### After activation, user can find out externally installed packages. As expected, it is empty. 
```
C:\Users\rasik>conda activate torch
(torch) C:\Users\rasik> conda list -n torch
# packages in environment at C:\Users\rasik\Anaconda3\envs\torch:
# Name                    Version                   Build  Channel
```
#### Install pytorch *[for deep Neural Networks]*
```
(torch) C:\Users\rasik>conda install pytorch
Collecting package metadata (current_repodata.json): done
Solving environment: done
## Package Plan ##
  environment location: C:\Users\rasik\Anaconda3\envs\torch
  added / updated specs:
    - pytorch
The following packages will be downloaded:
    package                    | build
    ---------------------------|-----------------
    _pytorch_select-0.1        | cpu_0           4 KB
....
    pytorch-1.6.0              | cpu_py37h538a6d7_0       101.1 MB
    vs2015_runtime-14.27.29016 | h5e58377_2        1007 KB
    wheel-0.36.2               | pyhd3eb1b0_0          33 KB
    ------------------------------------------------------------
                                           Total:       123.0 MB

The following NEW packages will be INSTALLED:
  _pytorch_select  pkgs/main/win-64::_pytorch_select-0.1-cpu_0
  blas             pkgs/main/win-64::blas-1.0-mkl
....
....
  pytorch          pkgs/main/win-64::pytorch-1.6.0-cpu_py37h538a6d7_0
  wincertstore     pkgs/main/win-64::wincertstore-0.2-py37_0
  zlib             pkgs/main/win-64::zlib-1.2.11-h62dcd97_4

Proceed ([y]/n)? y
Downloading and Extracting Packages
mkl_random-1.0.4     | 287 KB    | #################### | 100%
_pytorch_select-0.1  | 4 KB      | #################### | 100%
mkl-service-2.3.0    | 45 KB     | #################### | 100%
....
pytorch-1.6.0        | 101.1 MB  | #################### | 100%
libmklml-2019.0.5    | 17.5 MB   | #################### | 100%
Preparing transaction: done
Verifying transaction: done
Executing transaction: done
```
### Launch Jupyter notebook
```
(torch) C:\Users\rasik>jupyter notebook
    To access the notebook, open this file in a browser:
        file:///C:/Users/rasik/AppData/Roaming/jupyter/runtime/nbserver-21512-open.html
.....
[W 16:21:25.895 NotebookApp] 404 GET /nbextensions/widgets/notebook/js/extension.js?v=20210109162058 (::1) 2.99ms referer=http://localhost:8888/notebooks/Untitled.ipynb?kernel_name=python3
[I 16:23:25.811 NotebookApp] Saving file at /Untitled.ipynb
```
### Handling error in loading environment
**Often we note that despite launching jupyter from virtual environment, jupyter launches in base environment**
* So, as noted below, *import torch* is not recognised inside a newly opened jupyter notebook
<img src="/images/p2/output_2_1.png">
* This happens because jupyter kernel attached with new conda environment does not exist. **To overcome this situation, we have to manually add a kernel with a different version of Python or a virtual environment.**

### Install ipykernel manually
```
(torch) C:\Users\rasik>pip install --user ipykernel
Collecting ipykernel
  Downloading ipykernel-5.4.2-py3-none-any.whl (119 kB)
     |████████████████████████████████| 119 kB ...
Collecting ipython>=5.0.0
  Downloading ipython-7.19.0-py3-none-any.whl (784 kB)
     |████████████████████████████████| 784 kB ...
.....
.....     
```
### Add conda environment to Jupyter kernel
* **As noticed, after running following commands, new kernel "torch" is detected and command *import torch* works successfully**
```
(torch) C:\Users\rasik>python -m ipykernel install --user --name=torch
Installed kernelspec torch in C:\Users\rasik\AppData\Roaming\jupyter\kernels\torch
```
<img src="/images/p2/output_2_2.png">
