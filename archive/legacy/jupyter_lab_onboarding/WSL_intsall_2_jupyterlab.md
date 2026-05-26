# Outline 
* basic orientation to linux enviroment through WSL on a windows machine
* Make a new directiory for projects
* Install miniconda (your package and virtual enviroment manager)
* Install some basic packages into your 'Base' enviroment
* Create and new enviroment 'not_base' 
* Install some more packages
* Start jupyter lab


# basic orientation to linux enviroment through WSL on a windows machine
## open terminal and open umbuntu

* install ubuntu in your wsl link below helps
https://ubuntu.com/tutorials/install-ubuntu-on-wsl2-on-windows-10#4-configure-ubuntu
* search for terminal in windows app start up
* power shell will start by defualt
* open a new tab by clicking the arrow next to the + icon
* select umbuntu
* a new tab should open with your umbuntu running in your WSL install

## some basic linux commands
``` 
# move to home directoy 
cd
# view content of home directiory 
ls
# view contents of home directory including hidden files that start with a period
ls -a
# move to some other folder in the current directory
cd other_folder_name
# move to some other directory anywhere else in the WSL filesystem
cd full_path_to_the_parent_directory/directory_somewhere_else
# view full path of current location
pwd
```

## pin your WSL world's home directory to your windows file explorer 
* open a ubuntu terminal
``` 
# move to home directoy should already be there
cd
# run this command in a ubuntu terminal
# it will open up a windows file explorer in showing the location of your WSL home in the windows world file system
explorer.exe .
```
* pin the current location to quick acess by right clicking on 'network' in the left column
select 'pin to quick acesss'

# Make a new directiory for projects

``` 
# go back to WSL world home directoy 
cd
# make new directory for all you jupyter notebook projects
mkdir projects
# check to see if new directory is there 
ls 
# move into new directory
cd projects
# now make a new folder for tutorials
mkdir tutorials

# now move into the new tutorials folder
cd tutorials
# check current location
pwd 
# now move up one directory back into the projects folder with the .. relative path whcih means up one direcotry  
cd .. 
# verify you have moved back into the project folder 
pwd
# now go back to home directory before moving on 
cd
```

# Install miniconda (your package and virtual enviroment manager)

https://docs.conda.io/en/latest/miniconda.html




* run wget (think of it as web get download ) command
``` 
# make sure you are currently in youre home directory
cd 
pwd
# wget <download url for linux (right click on first linux link and select 'copy link adress')>
 wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
 ``` 

* check that downloaded file is not currupted or incomplete
* verfiy result of sha256sum matches the value on the website the value for our example at time of writing is below
``` 
# run sha256sum <name of downloaded file (Miniconda3-latest-Linux-x86_64.sh)>
sha256sum Miniconda3-latest-Linux-x86_64.sh
# aef279d6baea7f67940f16aad17ebe5f6aac97487c7c03466ff01f4819e5a651
``` 
* run the downloaded file to install the miniconda package manager
```
bash Miniconda3-latest-Linux-x86_64.sh

```
# Get started in your base enviroment

## Install some basic packages into your 'Base' enviroment


* set the channel prioritied (where conda will download things from)
``` 
conda config --add channels conda 
conda config --add channels conda-forge 
conda config --add channels bioconda
```
* 
```
conda install pandas seaborn scikit-learn statsmodels numba scikit-learn-intelex matplotlib r-base scipy numpy 
conda install jupyterlab ipykernel ipywidgets nb_conda_kernels r-irkernel
```

# Create and new enviroment 'not_base' 

``` 
conda create -n not_base python=3.8
conda activate not_base
conda config --add channels conda ; conda config --add channels conda-forge ; conda config --add channels bioconda
```
# Install some more packages

``` 
conda install pandas seaborn scikit-learn statsmodels numba scikit-learn-intelex matplotlib r-base scipy numpy 
conda install ipykernel ipywidgets nb_conda_kernels r-irkernel
```


# Start jupyter lab

``` 
jupyter lab
```
