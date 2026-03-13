# Setting up for the workshop(s)

First of all: clone or download this GitHub repository.

For data, please use
[this dataset](https://www.10xgenomics.com/datasets/pbmcs-3p_citrate_cpt-3-1-standard).
This is a fairly recent publicly available datset from 10X Genomics.
Make sure to download all the **"Output and supplemental files"**
and place them in a recognizable folder
(such as `data/PBMC-10X', `pbmc`, `260318workshop`, ...).

For the workshop, we will be using the clustering tutorial from
[scanpy](https://scanpy.readthedocs.io/en/stable/tutorials/basics/clustering.html).
We have already prepared a copy in this repository for your convenience.
There will be some minor changes that we will make on-the-go.

As for setting up Python itself. 
If you just want to set up a package manager for our
exercises/notebooks that "just works", follow these steps:
* Go to Anaconda.org and download the Anaconda installer. Follow its guided tutorial to install `conda`. Make sure to read through the tutorial carefully!
* Clone or download this repository, make sure you have the
`environment.yml` file.
* Run this: `conda env create -f environment.yml` ( `environment.yml`
is in the repository you just cloned/downloaded).
* Finally, activate the newly created environment with `conda activate bioinfo-forum` whenever you want to use it.

This should be sufficient for all of our exercises, and likely many of your future bioinformatics needs as well.

For IDEs, you should have access to `jupyter notebook` and
`jupyter lab` on the command line after you activate conda.
Both of them are largely interchangeable for our purposes.

If you are interested in more details on Python, 
read the other provided Markdown file `python.md`.

If you have extensive experience with Python, you can just set things
up however you see fit instead. We will be using fairly standard
`scanpy` and `scverse` libraries, which you should already have
installed somewhere.
