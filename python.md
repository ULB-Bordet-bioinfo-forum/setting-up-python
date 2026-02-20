# Setting up a Python bioinformatics environment for the exercises

## TL;DR

If you just want to set up a package manager for our
exercises/notebooks that "just works",
follow these steps:
1. Go to Anaconda.org and download the Anaconda installer.
Follow its guided tutorial to install `conda`.
Make sure to read through the tutorial carefully!
2. Clone this repository, or download the provided `environment.yml` config file.
3. Run this: `conda env create -f environment.yml` (
`environment.yml` is the file you just downloaded).
4. Finally, activate the newly created environment with
`conda activate bioinfo-forum` whenever you want to use it.

This should be sufficient for all of our exercises,
and likely many of your future bioinformatics needs as well.

If you are interested in more details, read on.


## Why all this discussion about Python & package management anyway?

I'm unfortunately not an expert in Python history, but
due to various circumstances, Python's package management ecosystem
is - without sugarcoating it - a complete mess. 
The fact that many bioinformatics packages are maintained
by a skeleton crew (if maintained at all) makes 
package management more necessary, and thus further
complicates the mess.
Someone far more
knowledgeable about Python than me has
[written about this in a blogpost which you can read more about](https://chriswarrick.com/blog/2023/01/15/how-to-improve-python-packaging/#pypa-versus-reality-packaging-survey-results-and-pypa-reaction).

Generally, you should **never** install anything on your system or global
Python distributions. To begin with, installing too many packages
on the system Python would make your system run slower.
More seriously: many Python packages require complex
dependency resolution or even downgrading your Python version
for them to work, meaning that in extreme cases you can
theoretically "brick" your computer by installing some
machine learning packages.


## Installing Python itself

If you are using Windows or MacOS, the easiest way to install
Python is to go to 
[python.org/downloads/](https://www.python.org/downloads/)
and download the latest version. The installer should guide you
through the rest of the steps.

In general, it is usually a good idea to install the *latest* or
*second-latest*
version of Python for a global Python install. 
Using a new but not the newest version can sometimes help
with software compatibility issues. 

You should refrain from using Python versions that are too old.
Using an overly
outdated software can lead to accumulation of tech debt over time,
which may cause strange software dependency and other issues
in the long run.
Unfortunately the definition of "too old" can be quite subjective;
if it is possible, the easiest way is to stick to the latest version.

If you are on Linux, you should install Python using your 
distribution's package manager (`apt`, `dnf`, `pacman`, ...)
instead, and *only* install Python this way. Having too many
Pythons installed via different methods can lead to 
strange computer issues.
Most likely Python is already installed on your computer.
Beware that depending on your Linux distribution,
you may not have access to the latest Python version... or may
have access to *nothing but* the latest Python version.


## Package management

In general, it is quite important in any software-related
projects to have a package manager that helps with automatic
updates, version control, etc...
We have recommended a few approaches below.
There are more comprehensive comparisons of the different
package management tools such as
[this blog post](https://alpopkes.com/posts/python/packaging_tools/)
if you are interested in more details, or want to try
one of the other fancier methods.


### Conda (recommended, despite its issues)

Arguably the most popular Python package manager for
scientific programming and data science. In fact, Anaconda
was designed very specifically *for* scientific programming.
Most likely you will be using one of Anaconda, miniconda, or
miniforge, depending on what computer system you are running
and how nuts you are about free and open software.

Unfortunately for us, `conda` is also a massive headache to deal with
as an end-user, but due to its popularity we all have to have
at least a passing knowledge of it.

To set up conda:
depending on your operating system and preference, you may choose to
use Anaconda's guided installer, use another conda (such as
`miniforge`) hosted
on your distribution's software repository, or do something 
else (we will not help you with compiling conda from source, sorry).
In any case: `conda` needs to be activated in order for it to work.
Usually people add it to their shell startup config (such as `.bashrc`)
so that conda automatically starts whenever you open a terminal:
Anaconda's installer will do this automatically for you.

To create an environment, run `conda create -n <env_name> <list_of_packages>`.
`<env_name>` is the literal name you assign to the environment. Make
sure it is short and simple, because you will have to activate
the environment by typing its name every time.
`<list_of_packages>` is the list of packages you want installed into this
environment. You can always add more later, but it doesn't hurt to 
install them immediately if, say, you **know** you need to use `scanpy` and
`matplotlib` to do your work. Conda will do the dependency resolution for you.

You can also set up an environment with a configuration
file: we provided one in this GitHub
repository that included some commonly used single cell packages, as well
as some Jupyter utilities that you can use as an IDE for coding.
In that case, run `conda create -f <config_file>` instead.

To manage/maintain an already built environment, here are a few useful
commands:
* `conda install <package_names>`: install a package. Conda
will do the rest for you.
* `conda install -c <channel> <package_names>`: similar to above, but
we are specifying that conda will also consider packages
from the named channel.
This can be any valid channel name, but the most relevant ones
for us are `conda-forge` and `bioconda`.
* `conda update`: update packages in this environment, you can also specify
package names so that conda only updates certain packages.


### Just use Python's built in virtual environments

... yes, you can just use Python itself. In fact, this is what
Python (as in the organization) officially endorses.

This method involves using Python's very own built-in tools
to create a "virtual environment", which can be seen as
an independent Python setup or a setup specific to a project.

Setting up is easy, just run `python -m venv <environment_name>`. 
`<environment_name>` will be created as a new directory where your
environment will be stored, so try to make it obvious (for example,
`scverse` for a single cell project that uses scverse tools). 
Note that you shouldn't change the location of this directory
after you create it, otherwise the virtual environment will break.

You can then let your system use this environment
by executing the "activate" file with:
* MacOS/Linux: `source <directory_name>/bin/activate`
* Windows: `<directory_name>\bin\activate`

Once the environment is activated, you can install things into it
using Python's native package manager, `pip`: they
will be installed specifically to this virtual environment instead.
Just don't forget to activate this environment every time you 
want to use it.

Note that there is also `virtualenv` which is a third-party tool
that is **distinct** from python's built-in `venv`.


### uv

The "cool kid on the block", supposedly far superior to other
package managers on the market. If you go to any Python meetups
chances are someone will be glazing it. Unfortunately
none of the organizers have extensive experience using `uv`, but
it is allegedly really good and trivially easy to set up,
so feel free to give it a try. If you have some positive
experience with `uv`, please feel free to add to this
readme file.

Download link: [docs.astral.sh/uv](https://docs.astral.sh/uv/)



