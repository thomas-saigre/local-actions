# local-actions

Some actions automatically run by git on commit or push.

The script given in subdirectories is to add in the folder `.git/hooks` of your repository.
More information [here](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks).


- [publish-LaTeX](publish) : send on a server via `scp` pdf files (compiled by LaTeX or not) in set directories, only if the files are changed.


