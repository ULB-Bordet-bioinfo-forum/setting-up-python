# Setting up for the workshop(s)

First of all: clone or download this GitHub repository.

For data, please use
[this dataset from 10X](https://www.10xgenomics.com/samples/cell-exp/1.1.0/pbmc3k/pbmc3k_filtered_gene_bc_matrices.tar.gz).
This is a classical "toy" dataset of PBMC offered by 10X Genomics.
If you have trouble accessing this link, try registering
an account on 10X Genomics' data portal first (it will be
useful, trust me!).
Make sure to place the downloaded data in a recognizable folder
(such as `data/PBMC3k/`, `pbmc/`, `260318workshop/`, ...).

For the workshop, we will be using the clustering tutorial from
[scanpy](https://scanpy.readthedocs.io/en/stable/tutorials/basics/clustering.html).
We have already prepared a copy in this repository for your convenience.
There will be some minor changes that we will make on-the-go,
but for reproducibility purposes we did not change the notebook itself.

As for setting up Python itself. 
If you just want to set up a package manager for our
exercises/notebooks that "just works", follow these steps:
* Go to [Anaconda.org](https://anaconda.org/) and download the Anaconda installer.
Follow its guided tutorial to install `conda`. Make sure to read through the tutorial carefully!
* Clone or download this repository, and make sure you have the
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
