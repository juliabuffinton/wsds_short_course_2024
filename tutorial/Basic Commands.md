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

### Add a README file, Track it

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

1. Using a text editor of your choice, or the command line, enter the following text:

```
# Using Tools for Effective Open Science Collaboration: GitHub

This is a sample repository created during the WSDS 2024 Short Course titled "Using Tools for Effective Open Science Collaboration: GitHub". 

Here I will practice basic git commands, branching and merging, and remote repository collaboration

```


# Later
 because then we can also get familiar with Github, and it is (in my opinion) a little easier to set up.

1. Go to [Github.com](https://github.com) and create a new repository by clicking the green "New" button on the left side.
2. Give your new repo a fun name! Git will suggest one; take its suggestion by clicking on the green text after "How about...?"
3. Make sure your repo is public and check "Add a README file" under the Initialize header. Create your repository.

Tada!





## Configure Repo
Every repo is different, and there are many ways to configure each to meet their specific need. 

1. Go to "Settings" along the top menu bar.
2. On the first page ("General") make sure your default branch is set to `main`. If not, change it!
3. Under "Code and automation" click on "Branches". Practice adding a branch protection rule where the "main" branch requires a pull request before merging. **Do not save!** This is a best practice for individual and collaborative code development; it's a handy guardrail preventing accidental pushes of code to the production branch. For more about branch protection, visit [this link](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/managing-a-branch-protection-rulegit).

## Clone Your Repo

1. In Git Bash or terminal, navigate to the directory you'd like to put this repo in (e.g., the directory that will be the parent of your repo). **It is very important that you do NOT clone this repository into an existing git-tracked repository.**

   Option A: using file explorer, navigate to the directory. Copy the address. In Git Bash, type `cd ` (note the space after cd) and then paste the address (SHIFT+INS).
   Option B: within Git Bash, navigate to your directory using `cd ` command.

2. In Github, go back to "Code" in the top menu bar.
3. Click the green "<> Code" button in the upper right. Make sure you are on the **HTTPS** tab (we haven't set up SSH); copy the URL to your clipboard.
4. In Git Bash, type `git clone ` (note the space after clone) and then paste (SHIFT+INS) the URL. 
5. Navgiate into to that repository by typing `cd <your_repo_name>`.

## Practice!
Now, we are going to practice a few basic commands in git.

### Make some local changes
1. Open up your README file in your preferred editor (VS Code, Notepad, vim, etc.).
2. Add the following line: `This is a sample README for WIDS DC 2024. In it, I will write some simple python code, edit it, and track changes.`
3. Commit this change by going back to Git Bash, typing `git add README.md`. (you can always check the status of any file you've edited by typing `git status`)
4. Type `git commit -m "modify readme"`.
5. Create a new file called `hello.py`. Edit that file to add the python code `print("hello world")`. Save.
6. Commit this change by going back to Git Bash, typing `git add hello.py` (pro tip: most terminals/Git Bash have tab complete) then `git commit -m "create hello.py; print hello world"`
7. Check your log! What have you done so far? Type `git log --oneline`. The oneline flag will make it display each commit on one line which makes it easier to read.
8. Add another line to your README, "I am learning git!".
9. Before staging and committing that file, check what changed by typing `git diff README.md`.
10. Then, add the file to the staging area and the commit it with a helpful message.

### Push your changes to the remote repo
1. Type `git push`. Enter any credentials you are prompted for.
2. Navigate to the remote repository in your browser (there will be a link the second-to-last line in the output after you push. Check to make sure your changes are there!

### Make a new branch
Now, create a new branch to change the code in our `hello.py` file.

1. Create a new branch by typing `git branch -b change_hello_msg`. This will create the new branch; the `-b` flag also immediately switches to that branch.
2. Edit the hello.py file to change "world" to "WiDS".
3. Add and commit the file.
4. Switch back to your main branch by typing `git checkout main`. Check the file again - has the text changed?
5. Merge your changes into the main branch by typing `git merge change_hello_msg`.
6. Check the log by typing `git log --oneline --graph`. You should see each commit on main, where we branch to the new branch, commits made there, and when it comes back together.
7. Push your changes to the remote repository and check them out in Github!
