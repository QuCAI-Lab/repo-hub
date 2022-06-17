<br />
<div align="center"> 
  <a href="https://docs.conda.io/en/latest/"><img align="center" src="https://avatars.githubusercontent.com/u/3571983?s=200&v=4" alt="camponogaraviera" height="200" width="200" /></a>
  <h1> Conda Essentials </h1>
</div>

<h3 align="center"> For more information, resort to the <a href="https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdf">Conda Cheat Sheet</a>.</h3> 

<br />

# Anaconda Prelims

Beware: the angle brackets punctuation mark denoted by "`<>`" (voiced chevrons) is only used as a placeholder, i.e, it's not a special character.

1. Download [Anaconda](https://www.anaconda.com/products/individual).

2. With open Terminal, navigate to the path of the file directory and grant execute permission (for die hard [Unix-like users](https://github.com/QuCAI-Lab/educational-resources/tree/main/Linux_Essentials)): 

```bash
cd <dir_pathname> && chmod +x <filename>.sh
```

3. Install Anaconda via terminal (Ubuntu users):

```bash
./<filename>.sh
```

Install example (if you're coming from the future, check the latest version):
```bash
cd ~/Downloads && chmod +x Anaconda3-2021.11-Linux-x86_64.sh && ./Anaconda3-2021.11-Linux-x86_64.sh
```

- To update conda

```sh
conda update -n base conda -y 
```
or
```sh
conda update -n base -y conda
```

- To create a brand new conda environment with an exact python version (e.g., V3.8.3):

```sh
conda create -n <env_name> python==3.8.3
```
Note: the `==` constraint type specifies an exact package version.

- To show conda env. directories:

```sh
conda config --show envs_dirs
```

- To list available channels:

```sh
conda config --show channels
```

- To create a new environment and install an exact package version from a different conda channel (e.g., conda-forge):

```sh
conda create --channel conda-forge --name <env_name> <package_name>==version
```
or
```sh
conda create -c conda-forge -n <env_name> <package_name>==version
```
[Tip](https://docs.conda.io/projects/conda/en/latest/user-guide/concepts/conda-commands.html): one can abbreviate the double dash flag `--` to a single dash followed by the first letter of the command option. E.g., `--name` is the same as `-n`, and so on.


- To install more than one exact package version in a specified conda environment:

```sh
conda install -n <env_name_exist> <package_name1>==version <package_name2>==version
```

- To update a package within the root environment:

```sh
(env_name) conda update <package_name>
```

- To update a package from the base environment:

```sh
(base) conda update -n <env_name> <package_name>
```

- To list available environments:

```sh
conda info -e
```
or
```sh
conda env list
```

- To list and show info of all packages in a conda environment:

```sh
conda list -n <env_name_exist>
```

- To list and show info of a linked package from a conda environment:

```sh
conda list -n <env_name_exist> <package_name>
```

- To activate (log in) a conda env.: 

```sh
conda activate <env_name_exist>
```

- To show the current environment info:

```sh
conda info
```

- To list installed packages:

```sh
conda search <package_name>
```
Note: `conda info package_name` is deprecated.

- To list all the installed packages in the current environment:

```sh
conda list 
```

- To list a specific package in the current environment:

```sh
conda list <package_name>
```

- To install a package from a different conda channel in the current env.:

```sh
conda install --channel <channel-name> <package_name>
```

- To add conda-forge channel to the `.condarc` file:

```sh
conda config --add channels conda-forge
```

- To list the history of each change to the current environment:

```sh
conda list --revisions
```

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

- To build an **identical conda env.** from the aforementioned spec file:

```sh
conda create --name <env_name> --file <filename>.txt
```

- To export the current environment package dependencies to a .yml file (**suggested for [sharing](https://conda.io/projects/conda/en/latest/user-guide/concepts/environments.html#share-an-environment) between users**):

```sh
conda env export --from-history -n <env_name_exist> > environment.yml
```

- To create a brand new conda env. with pre-defined package dependencies from the `environment.yml` file:

```sh
conda env create -n <env_name> environment.yml
```

- To deactivate the current environment:

```sh
conda deactivate
```

- To remove a conda environment:

```sh
conda env remove -n <env_name_exist>
```
or (due to issue [#3215](https://github.com/conda/conda/issues/3215))
```sh
conda remove --name <env_name_exists> --all
```

# Contributors 

Created and maintained by [@camponogaraviera][1].

[1]: https://github.com/camponogaraviera
