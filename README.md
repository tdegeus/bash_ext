# bash_ext

Wrappers around BASH functions.

# Contents

<!-- MarkdownTOC -->

- [Functions](#functions)
    - [`lsnum`](#lsnum)
    - [`lslist`](#lslist)
    - [`extract`](#extract)
    - [`efind`](#efind)
    - [`mv_regex`](#mv_regex)
    - [`rm_regex`](#rm_regex)
    - [`cp_regex`](#cp_regex)
    - [`rm_build`](#rm_build)
    - [`pstat`](#pstat)
- [Installation](#installation)

<!-- /MarkdownTOC -->

# Functions

## `lsnum`

Print the output of the `ls -lh` command, whereby the file-permissions are printed as numbers.

The numeric value of the permissions follows from summing the numeric value of each of the permissions, which are:

|         | Owner | Group | Others |
| ------- | :---: | :---: | :----: |
| Read    |  400  |  040  |  004   |
| Write   |  200  |  020  |  002   |
| Execute |  100  |  010  |  001   |

For example `-rwxr--r--` the following numerical value `744`, which breaks down as follows:

* Owner: `Read + Write + eXecute = 400 + 200 + 100 = 700`.
* Group: `Read = 040`.
* Others: `Read = 004`.

## `lslist`

Print the output of the `ls` command as list.

## `extract`

Automatically extract a (compressed) archive.

## `efind`

Find files with specific extensions.

## `mv_regex`

The move command, but allow regular expression. This allows one to partly rename a batch of files.

## `rm_regex`

The remove command, but allow regular expression. This allows one to selectivity remove a batch of files.

## `cp_regex`

The copy command, but allow regular expression. This allows one to selectivity copy a batch of files.

## `rm_build`

Remove some common temporary build files. The user is prompted before actual removal.

## `pstat`

Parse the output of `ps` is a human readable manner.

# Installation

To get these scripts to work one can:

-   Point the `$PATH` to this repository's location, for example by adding the following line to the `~/.bashrc` (or `~/.zshrc`):
  
    ```bash
    export PATH=/path/to/bash_ext:$PATH
    ```

-   'Install' the script:
  
    1.  'Install' the scripts:
  
        ```bash
        cd /path/to/bash_ext
        mkdir build
        cd build
        cmake .. 
        make install
        ```
     
-   'Install' the script in your home folder:
  
    1.  Create a directory to store libraries in the home-folder. For example:
  
        ```bash
        mkdir ~/opt
        ```

    2.  'Install' the bash_ext's scripts. For example:
  
        ```bash
        cd /path/to/bash_ext
        mkdir build
        cd build
        cmake .. -DCMAKE_INSTALL_PREFIX:PATH=$HOME/opt
        make install
        ```
