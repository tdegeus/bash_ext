# bash_ext

Wrappers around BASH functions.

## Contents

<!-- MarkdownTOC -->

- [`lsnum`](#lsnum)

<!-- /MarkdownTOC -->

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

