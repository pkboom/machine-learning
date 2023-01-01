# Anaconda

## Installed kernelspec golden_scenario_env

/Users/keunbae/Library/Jupyter/kernels/golden_scenario_env

# Install package with the channel

```sh
conda install scikit-learn -c conda-forge -U

conda install python==3.10 # install version 3.10

conda remove python

conda list [<package>]
```

# Use environment in Jupyter notebook

You need to setup the environment as an ipykernel to use it from the Jupyter notebook.
To do it run inside of the conda activated environment:

```sh
python -m ipykernel install --user --name sklearn_env --display-name "Sklearn Env"
```

# Conda Environment

```sh
## Create an environment
conda create -n sklearn-env -c conda-forge scikit-learn
# Create an environment named sklearn-env containing scikit-learn
# -c: Additional channel to search for packages.

# Activate it
conda activate sklearn-env

# List all the conda environment available

conda info --envs

# Create new environment named as `envname`

conda create --name envname

# Remove environment and its dependencies

conda remove --name envname --all

# Clone an existing environment

conda create --name clone_envname --clone envname

#Create environment.yml file via conda
conda env export > environment_droplet.yml

# create a conda environment from a file

conda env create -f environment.yml

# update a conda environment with a file
conda env update --file environment.yml
```
