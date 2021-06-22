# HPC

Useful instructions / commands for the HPC shell. For starting please check the [Techne Site](https://sites.google.com/case.edu/techne-public-site/cwru-hpc-orientation). 

Quick Start [here](https://sites.google.com/a/case.edu/hpcc/hpc-cluster/quick-start).

## Table of Contents
- [HPC](#hpc)
  - [Table of Contents](#table-of-contents)
    - [Accessing the HPC](#accessing-the-hpc)
    - [Useful Shell Commands](#useful-shell-commands)
      - [Available Modules](#available-modules)
      - [Access to GPU](#access-to-gpu)
    - [Access to Tensorflow](#access-to-tensorflow)

### Accessing the HPC

There are majorly 3 ways of accessing the HPC provided at Red Hen Lab:

1. OnDemand Portal: The OnDemand portal on the web [here](https://ondemand.case.edu/) provides access to the HPC cluster and is the best possible way to access anything on the HPC. It not only provides a shell access, but also access to directories where files can be downloaded using a GUI, a desktop access (with/without GPU as per requirement), and some features such as jupyter notebooks, and some more.
2. Terminal Access from local computer: It is done with the help of a VPN. Same as the HPC shell access. For the VPN setup, check [here](https://sites.google.com/case.edu/techne-public-site/cwru-hpc-orientation/access-cwru-hpc-via-vpn). *The format for the password for VPN access to HPC is as follows: ```hpc_passphrase,duo_code``` which needs to be followed for successful connection through VPN. Connection certificate is not required and can be ignored.
3. X2Go GUI Interface: It is a desktop application that provides access to the HPC. Check [here](https://sites.google.com/a/case.edu/hpcc/hpc-cluster/hpc-visual-access/x2go) for more info.

1 and 2 have worked for me. I haven't had success with 3. However, for all the 3 ways, Duo authentication (similar to Google Authenticator) is required. Follow all the steps except the VPN step [here](https://sites.google.com/case.edu/techne-public-site/cwru-hpc-orientation/access-cwru-hpc-via-vpn) to get the Duo setup.

### Useful Shell Commands

Most of the commands are similar to any Linux bash commands. I will list a few important/required during the work.

_Note: Root access is denied in the HPC_

#### Available Modules
```
$ module avail
```

#### Access to GPU
```
$ module load cuda                          # Default Cuda version loaded
$ module load cuda/10.1                     # Specific Cuda version loaded
$ srun -p gpu --gpus 1 --mem 4000 --cpus-per-gpu 2
```

### Access to Tensorflow
```
$ module load gcc
$ module load python/3.7.0
$ module load cuda/10.1
$ module load tensorrt/6
$ python
>>> import tensorflow as tf
>>> tf.__version__
2.1.0                                       # As per June 2021
```