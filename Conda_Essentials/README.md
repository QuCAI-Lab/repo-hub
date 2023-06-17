<br />
<div align="center"> 
  <a href="https://docs.conda.io/en/latest/"><img align="center" src="https://avatars.githubusercontent.com/u/3571983?s=200&v=4" alt="camponogaraviera" height="200" width="200" /></a>
  <h1> Conda Essentials </h1>
</div>

<h3 align="center"> For more information, resort to the <a href="https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdf">Conda Cheat Sheet</a>.</h3> 

<br />

# Installing Anaconda

Note: the angle brackets punctuation mark denoted by "`<>`" (voiced chevrons) is only used as a placeholder, i.e, it's not a special character.

1. Download [Anaconda](https://www.anaconda.com/products/individual).

2. With open Terminal, navigate to the path of the file directory and grant execute permission (for die hard [Unix-like users](https://github.com/QuCAI-Lab/educational-resources/tree/main/Linux_Essentials)): 

```bash
cd <dir_pathname> && chmod +x <filename>.sh
```

3. Install Anaconda via terminal (Ubuntu users):

```bash
./<filename>.sh
```

Install example (check the [latest version](https://docs.anaconda.com/anaconda/install/hashes/lin-3-64/)):
```bash
cd ~/Downloads && chmod +x Anaconda3-2022.10-Linux-x86_64.sh && ./Anaconda3-2022.10-Linux-x86_64.sh
```

- To update conda

```sh
conda update -yn base conda
```

# Creating conda environments

- To create a brand new conda environment with an exact Python version (e.g., V3.8.3):

```sh
conda create -yn <env_name> python==3.8.3
```
Note: the `==` constraint type specifies an exact package version.

- To create a new environment and install an exact package version from a different conda channel (e.g., conda-forge):

```sh
conda create --channel conda-forge --name <env_name> <package_name>==version
```
or
```sh
conda create -c conda-forge -n <env_name> <package_name>==version
```
[Tip](https://docs.conda.io/projects/conda/en/latest/user-guide/concepts/conda-commands.html): one can abbreviate the double dash flag `--` to a single dash followed by the first letter of the command option. E.g., `--name` is the same as `-n`, and so on.

- To add conda-forge channel to the `.condarc` file:

```sh
conda config --add channels conda-forge
```

- To create a brand new conda env. with pre-defined package dependencies from the `environment.yml` file:

```sh
conda env create -n <env_name> environment.yml
```

- To create a conda env. from a spec file:

```sh
conda create --name <env_name> --file <filename>.txt
```

# Removing conda environments

- To remove a conda environment:

```sh
conda env remove -n <env_name_exist>
```
or (due to issue [#3215](https://github.com/conda/conda/issues/3215))
```sh
conda remove --name <env_name_exists> --all
```

# Activate/Deactivate

- To activate/work inside the environment:

```sh
conda activate <env_name>
```

- To deactivate the current environment:

```sh
conda deactivate
```

# Installing dependencies

- To install more than one exact package version in a specified conda environment:

```sh
conda install -yn <env_name_exist> <package_name1>==version <package_name2>==version
```
Note: without package version specification, Conda will install the latest version available in the Anaconda cloud.

- To install a package from a different conda channel in the current env.:

```sh
conda install --channel <channel-name> <package_name>
```

# Updating 

- To update a package within the root environment:

```sh
(env_name) conda update <package_name>
```

- To update a package from the base environment:

```sh
(base) conda update -n <env_name> <package_name>
```

- To update the conda environment after modifying the environment.yml file:

```sh
conda env update -f environment.yml --prune
```

# Listing environments, channels, and info

- To list available environments:

```sh
conda info -e
```
or
```sh
conda env list
```

- To list available channels:

```sh
conda config --show channels
```

- To show info about the current environment:

```sh
conda info
```

- To show conda env. directories:

```sh
conda config --show envs_dirs
```

- To list and show info of all packages in a conda environment:

```sh
conda list -n <env_name_exist>
```

- To list and show info of a linked package from a conda environment:

```sh
conda list -n <env_name_exist> <package_name>
```

- To list all the installed packages in the current environment:

```sh
conda list 
```

- To list a specific package in the current environment:

```sh
conda list <package_name>
```

- To list the history of each change to the current environment:

```sh
conda list --revisions
```

# Reverting, cloning and exporting

- To revert to a previous version:

```sh
conda install --revision <revision_number>
```

- To clone an env. named "env_name_exist":

```sh
conda create --name env_name_clone --clone env_name_exist
```

- To create a spec file containing all the env. package dependencies:

```sh
conda list -n <env_name> > spec_list.txt
```
or (if you activate the env.)
```sh
conda list > spec_list.txt
```
or (for a spec file containing the URLs of the package dependencies)
```sh
conda list -n <env_name> --explicit > spec_list.txt
```

- To export the current environment package dependencies to a .yml file (**suggested for [sharing](https://conda.io/projects/conda/en/latest/user-guide/concepts/environments.html#share-an-environment) between users**):

```sh
conda env export > environment.yml
```
To export only those packages installed with exact version specification:
```sh
conda env export --from-history -n <env_name_exist> > environment.yml
```

# Contributors 

Created and maintained by [@camponogaraviera][1].

[1]: https://github.com/camponogaraviera
