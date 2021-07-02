# Useful Singularity commands / info

Useful Info for Singularity Containers used in HPCs, specifically in Red Hen Lab, GSoC-21. Singularity Version: 3.5

For Introduction: Watch this video [here](https://www.youtube.com/watch?v=vEjLuX0ClN0).

### Table of Contents

- [Useful Singularity commands / info](#useful-singularity-commands--info)
    - [Table of Contents](#table-of-contents)
    - [Installation](#installation)
    - [Important File Extensions](#important-file-extensions)
    - [Important Commands](#important-commands)
      - [Load Singularity on HPC](#load-singularity-on-hpc)
      - [Run Singularity shell](#run-singularity-shell)
      - [Exec command](#exec-command)
      - [Run command](#run-command)
      - [Build command](#build-command)
    - [Other useful info:](#other-useful-info)

### Installation

Requires Singularity downloaded in a Linux OS only. [Link](https://singularity.hpcng.org/user-docs/3.5/quick_start.html) for downloading.

### Important File Extensions

- \*.sif : Singularity Image File [More info](https://singularity.hpcng.org/user-docs/3.5/quick_start.html#interact-with-images)

- \*.def : Singularity Definition File [More info](https://singularity.hpcng.org/user-docs/3.5/definition_files.html)

### Important Commands

Most commands are available on the Singularity [Documentation](https://singularity.hpcng.org/user-docs/3.5/introduction.html).

For starting, also check the [Techne Site](https://sites.google.com/case.edu/techne-public-site/singularity).

#### Load Singularity on HPC

```
$ module load singularity           # load the default version
$ module load singularity/3.5       # load the specific version
```

#### Run Singularity shell

It spawns a new shell inside the container and provides interaction with the container bash script:

```
$ singularity shell /path/to/container.sif          # simply go to the shell
$ singularity shell --nv /path/to/container.sif     # shell with access to GPU
```

This will load the shell, however the directory will not change to the HOME folder. It will remain in the same directory as it was previously. Go to $HOME using `cd /` and you will find certain new files/directrories such as `singularity` script file along with the directory named `.singularity.d`, which contains all the singularity files such as `./actions/shell, ./actions/run` (inside the above directory) which provide the dafault script for corresponding actions.

_Note: --nv provides container shell acess to GPU and can be used in any singularity command._

#### Exec command

The exec command runs the bash script inside the container and has access to all user-accessible files and folders inside it. It can run all commands that are defined inside the container. It is run from outside the .sif file.
For example:

```
$ singularity exec /path/to/container.sif echo "Inside the container"
```

#### Run command

This command runs the container script workflow:

```
$ singularity run /path/to/container.sif
OR
$ ./path/to/container.sif
```

#### Build command

Check [here](https://singularity.hpcng.org/user-docs/3.5/build_a_container.html)

Build from def file:
```
$ sudo singularity build /path/to/container.sif /path/to/def_file.def
```
Build from sandbox:
```
$ sudo singularity build --sandbox /path/to/container.sif /path/to/sandbox_directory
```
Build a sandox from sif file:
```
$ sudo singularity build --sandbox /path/to/sandbox_directory /path/to/container.sif
```

Note that singularity build always occurs as follows:
```
$ sudo singularity build [Options] <dest> <source>
```
Another important note: Requires root access and cannot be performed on the HPC.

### Other useful info:

* Certain commands such as run, exec, shell, etc. can bind external files and folders and have write access to them (if users themselves have the access).
* Singularity files and sandboxes can be very large, be sure to have atleast 10GB of secondary memory space available.
* By default, singularity loads a sh shell and not bash. Hence, commands such as `source` may not work. Use `.` instead of `source`. Eg: `. /env` and not `source /env`.
* You can use [Sylabs](https://cloud.sylabs.io/) to upload your images and also build images remotely from definition files, but you can't have the sandbox featue or change file permissions.