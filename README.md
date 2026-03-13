# Setting up Python for the workshop(s)

If you just want to set up a package manager for our exercises/notebooks that "just works", follow these steps:
* Go to Anaconda.org and download the Anaconda installer. Follow its guided tutorial to install `conda`. Make sure to read through the tutorial carefully!
* Clone this repository, or download the provided `environment.yml` config file.
* Run this: `conda env create -f environment.yml` ( `environment.yml` is the file you just downloaded).
* Finally, activate the newly created environment with `conda activate bioinfo-forum` whenever you want to use it.

This should be sufficient for all of our exercises, and likely many of your future bioinformatics needs as well.

If you are interested in more details, read the other provided Markdown file.
