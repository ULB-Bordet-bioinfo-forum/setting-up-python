# Setting up for the workshop(s)

First of all: clone or download this GitHub repository.

For the workshop, we have prepared a copy of all notebooks used
in this repository for your convenience.
These notebooks are directly inspired by various tutorials, 
including:
* [scanpy](https://scanpy.readthedocs.io/en/stable/tutorials/basics/clustering.html)
* And more we probably forgot to acknowledge.

As for setting up Python itself. 
If you are not super familiar with Python, we recommend you to follow
these steps:
* Go to [Anaconda.org](https://anaconda.org/) and download the Anaconda installer.
Follow its guided tutorial to install `conda`. Make sure to read through the tutorial carefully, especially if you have never used `conda` before!
* Clone or download this repository, and make sure you have the
`environment.yml` file.
* Go to the downloaded folder/repository, and run this on your console:
`conda env create -f environment.yml`
(`environment.yml` is in the repository you just cloned/downloaded).
* Finally, activate the newly created environment with
`conda activate bioinfo-forum` whenever you want to use it.

This should be sufficient for all of our exercises, 
and likely a good bit of your future bioinformatics needs as well.

For IDEs, you should have access to `jupyter notebook` and
`jupyter lab` on the command line after you activate conda.
Just type one of the above into the console after activating `bioinfo-forum`.
Both of them are interchangeable for our purposes.
If you are already familiar with VSCode/VSCodium, you can also use them:
they tend to be more feature-rich and user-friendly than Jupyter Notebook/Lab.

Finally:
if you have extensive experience with Python, you can just set things
up however you see fit instead. 
We will be using fairly standard
`scanpy` and `scverse` libraries, which you should already have
installed somewhere.
Just FYI that we won't offer hands-on support if you screw up your
fancy-pants `uv` setup or something like that, that is on you.


## Miscellaneous

Although not used as a part of the final workshop, I strongly
encourage you to also play around with
[this dataset from 10X](https://www.10xgenomics.com/samples/cell-exp/1.1.0/pbmc3k/pbmc3k_filtered_gene_bc_matrices.tar.gz),
This is a classical "toy" dataset of PBMC offered by 10X Genomics.
If you have trouble accessing this link, try registering
an account on 10X Genomics' data portal first (it will be
useful, trust me!).
10X Genomics hosts a myriad of other useful data to play around with as well.

If you are curious about Python's history with package management
(as well as why `conda` is so difficult to work with),
I wrote something in the separate `python.md` document.
