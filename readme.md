Conda environments contains a specified collection of packages, language agnostic allowing you to manage Python as well as R packages.

Kernels are programming language-specific processes that run independently and interact with the Jupyter notebook.
ipykernel is the wrapper around IPython. As of IPython 4.0, the language-agnostic parts of the project: the notebook format, message protocol, qtconsole, notebook web application, etc. have moved to new projects under the name Jupyter. IPython itself is focused on interactive Python, part of which is providing a Python kernel for Jupyter.

# Create an environment

```sh
# Create an environment named sklearn-env containing scikit-learn
# with a specific python version
# -c: Additional channel to search for packages.
conda create -n sklearn-env [-c conda-forge scikit-learn] [python=3.6]
# create the new environment without asking for confirmation
conda create --name play_environment pandas jupyter ipykernel python=3.7 pytorch pandas numpy=1.16 -y

# After creating your environment, you can install the packages you need besides the one already installed by conda.

# Activate an environment
conda activate sklearn-env

# Deactivate an environment
conda deactivate

```

# Install a kernel

```sh
# use ipykernel to register your new environment as a kernel named play_environment
(play_environment) $ python -m ipykernel install --user --name play_environment --display-name "play environment"

# install packages in conda environment
# -c: channel
# -U: update
# install version 3.10
(play_environment) $ conda install scikit-learn -c conda-forge -U python==3.10

# list all packages in the Conda environment
(play_environment) $ conda list [package-name]

# to list the history of each change to the current environment
(play_environment) $ conda list --revision

# revert to revision 0
(play_environment) $ conda install --revision 0

# Updating play_environment with TensorFlow 1.15 from base
(base) $ conda install -n play_environment tensorflow==1.15

# remove a package
conda remove python
```

# Config

```sh
# add the channel “conda-forge” to the .condarc
conda config --add channels conda-forge
```

# Clone an existing environment

```sh
conda create --name clone_envname --clone sklearn-env
```

# Reproduces Conda environment on the same operating system

The Spec list can be created with or without the explicit option, as shown below.

```sh
conda list >spec_list.txt
#or
conda list --explicit >spec_list_exp.txt
```

An explicit spec file shows the platform where the environment was created. This platform is the one where this spec file is known to work.

```sh
conda create --name test_spec --file spec_list_exp.txt
```

# Export Conda environments using environment.yml file

To share our project conda environment with other team members, we can use an export.
The environment.yml file is not operating system specific and formatted using YAML.

```sh
# Create environment.yml file via conda
conda env export > environment.yml

# If the environment already exists, then you will get an error.
# CondaValueError: prefix already exists

# create a conda environment from a file
conda env create -f environment.yml

# specify a different install path than the one specified in the ‘prefix’.
conda env create -f environment.yml -p .

# leave out the prefix line when generating the .yml file.
conda env export | grep -v "^prefix: " > pytorch_env.yml

# update a conda environment with a file
conda env update --file environment.yml

# Remove environment and its dependencies
conda env remove -n sklearn-env

# List all the conda environment available
conda env list
```

# Setup Jupyter Notebook In Conda Environment And Install Kernel

Let's say we created a conda environment `ml`.

```sh
$ conda activate ml
# ipykernel: IPython kernel for Jupyter
(ml) $ conda install ipykernel
# install the kernel to use a jupyter notebook
(ml) $ ipython kernel install --user --name=<any_name_for_kernel>

# uninstall a kernel
jupyter kernelspec uninstall play_environment

# kernels list
jupyter kernelspec list
```
