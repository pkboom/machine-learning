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
(play_environment) $ conda list

# to list the history of each change to the current environment
(play_environment) $ conda list --revision

# revert to revision 0
(play_environment) $ conda install --revision 0

# Updating play_environment with TensorFlow 1.15 from base
(base) $ conda install -n play_environment tensorflow==1.15

# remove a package
conda remove python

# list packages
conda list [<package>]

# uninstall a kernel
jupyter kernelspec uninstall play_environment

# kernels list
jupyter kernelspec list
```

# Config

```sh
# add the channel “conda-forge” to the .condarc
conda config --add channels conda-forge
```

# Clone or move conda environment

## Clone an existing environment

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

# update a conda environment with a file
conda env update --file environment.yml

# Remove environment and its dependencies
conda env remove -n sklearn-env

# List all the conda environment available
conda env list
```
