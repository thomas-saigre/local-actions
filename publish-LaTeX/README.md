# Publish LaTeX

This script is run after a commit.
It sends on a server via `scp` the pdf files (compiled by LaTeX or not) in set directories, only if the files are changed.

**NOTE :** The pdf files must be compiled before the commit.

## Configuration

Create a file `latex-dirs.txt` inside `.git/hook` containing the list of all directories of the repository with TeX sources. Example :

```
Report/2021
Talks
```
The pdf file synchronised on the server will be all PDF files inside these folders, excluding subdirectories.

The settings of `post-commit` script are :

* `SERVER` : name of the server where files are saved
* `USER` : username
* `SCP_PATH` : path where the files will be copied (eg `public_html/`)

An extra command can be run after the s-copy of the pdf (such as `majhome`). To set this command, use the alias `EXTRACMD`. If such a command is not necessary, you can either comment the `if` loop at the end of the file, or set `EXTRACMD='echo'` to print an empty line at the end.
