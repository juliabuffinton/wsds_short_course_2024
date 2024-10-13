# Tips and Tricks 
A collection of tips and tricks for issues you may encounter throughout the course of this training.

## Branches

1. If you already initialized a repository with the default branch of "master" but want to change to "main," run the following command: `git branch -m master main`. 


## Interacting with git bash

1. Copy and paste within git bash using `ctrl+insert` and `shift+insert`, respectively.


## Create files

1. You can use the `touch` command to quickly create an empty file - your machine will look for that file, and if it doesn't exist, create one. Don't forget the file extension!

2. If you want to create it using a command line text editor, `nano` or `vim` work well.

## Remove local repsitory

1. If you accidentally initialized a git repository in the wrong folder, un-git-ify it without deleting the whole folder by typing the following command to remove the `.git` diretory: `rm -r .git`.