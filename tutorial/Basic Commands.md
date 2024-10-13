# Tutorial: Basic Commands

## Create a Repo
There are multiple ways you might initiate a local git repository:
1. Create a new repository locally (that you might ultimately track remotely).
2. Create a new repository on the remote server (e.g., Github).
3. Clone an existing repostory on Github, either yours or someone else's.

We're going do this the first way, since all it requires is git on your own computer, no remote server necessary. By the end of this course, you'll have created git repositories three different ways!

### Initialize

1. Navigate to the folder where you want to set up git tracking in git bash. Note: you may need to create a new folder (`mdkir folder_name`) first! 
2. Type `git init`.
3. Check success:
   1. Message should say somehitng like `Initialized empty Git repository...`
   2. Git bash now shows `(main)` after directory. (If you see something else like `(master)`, refer to set up Tips and Tricks for how to change branch name).
   3. Type `git status`. It should tell you no commits yet and nothing to commit. (Indicator of failure to intialize would be a fatal error indicating you're not in a git repo.)

### Add a README file; track it

It's always a good practice to create a README file. The README acts as the first point of contact for anyone (Future You, peer, collaborator, etc.) who needs to understand the purpose of the project, how to use it, or how to contribute. 

Here we'll create one, set up git to track future changes, and add some details about our project.

1. Create README in your folder by typing the following command: `touch README.md`.
2. Check the status of this file using `git status`. This file isn't tracked yet (in fact, nothing in your repository is tracked), so any changes you make won't be be captured by git. 
3. To set up tracking, use the `git add README.md` command to track it. (Pro tip: tab complete works here for filenames!)
4. Check for success using `git status`. You'll now see this file under **Changes to be committed**.
5. Commit it! We're tracking it now but the file initialization isn't yet captured by git as an official checkpoint. To snapshot the status of the file now, type `git commit -m "Intialize README file"`. The `-m` flag adds a commit message.
6. Checking the status again (you know the command!), you'll no longer see the file listed - this is because there are no new changes made since we have committed it. Instead, you'll see that your branch is ahead of the origin (more on that later...) by 1 commit. 

### Modify README file

An empty README isn't particularly useful. Let's add some text to it!

1. Using a text editor of your choice, or the command line, enter the following text in your README file:
```
# Using Tools for Effective Open Science Collaboration: GitHub

This is a sample repository created during the WSDS 2023 Short Course titled "Using Tools for Effective Open Science Collaboration: GitHub". 

Here I will practice basic git commands, branching and merging, and remote repository collaboration.
```
(Pro tip: pasting in vim can be done using `Shift+Insert`.)

2. Check the status again, and you'll see that modified the readme file. 
3. Add the changes you've made to be staged for commit, using `git add README.md`.
4. Realize that we typed 2023, when we meant 2024! Edit your file again to correct the year.
5. Double check to make sure we edited what we needed to by comparing against the previous version we added. Use the `git diff` command to show the lins of text that were changed. You should see the line with 2023 in red indicating it was removed, and the lin with 2024 in green indicating it was added.
6. Add the README file to be staged for commit.
7. Commit the file with a descriptive message, such as `git commit -m "add text to README file"`.