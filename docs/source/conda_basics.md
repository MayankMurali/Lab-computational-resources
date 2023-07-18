
# Managing dependencies with conda

Conda is an open source package management system and environment
management system that runs on most operating systems.

### Initialising a terminal for use with conda

Sometimes the terminal is not configured to run with **conda** right
away. To configure your terminal for use with **conda** run the
following 2 commands:

``` bash
# Initialise the terminal for use with conda
conda init bash

# Programmatically close/reopen your terminal window for changes to take effect
exec -l bash
```

### **Creating a new empty conda environment for isolating project dependencies**

To prevent having a very large unified installation environment and use
dedicated environments for each one of your projects it is a suggested
good practice to create separate conda environments. To create an empty
environment **named** **`my-new-env`** use the following command:

``` bash
conda create --name my-new-env
```

### **Creating a new conda environment from a metadata file of dependencies (environment.yml)** {#creating-a-new-conda-environment-from-a-metadata-file-of-dependencies-environmentyml}

Some times it\'s more practical to install dependencies for a project
from a metadata file, often named `environment.yml` by convention.

The file is in YAML format, and contains 3 important pieces of
information:

1.  **name:** of the environment\
2.  **channels:** specific registries where the libraries are deposited,
    some examples are `conda-forge` and `bioconda`.\
3.  **dependencies:** the libraries

The a simple **environment.yml** file would look like this:

``` yaml
name: my-new-env
channels:
  - conda-forge
  - bioconda
  - r
dependencies:
  - python
  - r-base
  - r-devtools=2.2
```

To **create** or even **update** an environment with the name
`my-new-env` and the dependencies listed in the above file we can use
the following commands respectively:

``` bash
conda env create --file environment.yml
conda env update --file environment.yml
```

We can overwrite the name of the environment defined in the YAML file by
using the `--name` flag and a new name for our environment like so:

``` bash
conda env create --name publication-env --file environment.yml
```

### How to list all available conda environments in a workspace

We can use the following command:

``` bash
conda env list
```

### How to select and use (activate) a specific conda environment

After listing all environments, we can select at any time which one we
want to use and switch into that specific environment with the command:

``` bash
conda activate my-env
```

### How to install libraries in this conda environment:

After activating a given **conda** environment, we can directly install
a package or library in this environment with the command:

``` bash
# don't specify a channel to search
conda install r-base

# specify in which channel to search for the dependency
conda install --channel conda-forge r-base
```


### How to search for the names of the libraries, 2 ways

1.  **GUI:** By visiting the
    [https://anaconda.org/](https://anaconda.org/cgpu/dashboard)
    website. You can use the search field and type the name of the
    dependency you are looking for eg `tidyverse`
2.  **CLI:** Using the command line interface by typing:

``` bash
conda search tidyverse
conda search --channel conda-forge tidyverse
```

