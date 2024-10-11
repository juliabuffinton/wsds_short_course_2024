# Using Tools for Effective Open Science Collaboration: Github.
For participants in the WSDS Short Course, Using Tools for Effective Open Science Collaboration: Github.

## Set Up

1. Open up Git Bash (Windows) or terminal (Mac/Linux). Type the following commands (press enter between each) to set your name and email. Change "Your Name" and "Your Email" to your actual name and email, or whatever you would like displayed alongside your commits.

`git config --global user.name "Your Name"`

`git config --global user.email "Your Email"`

## Create a Repo
There are multiple ways you might initiate a local git repository:
1. Create a new repository locally (that you might ultimately track remotely).
2. Create a new repository on the remote server (e.g., Github).
3. Clone an existing repostory on Github, either yours or someone else's.

We're actually going to do this the second way, because then we can also get familiar with Github, and it is (in my opinion) a little easier to set up.

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
     1.  Option A: using file explorer, navigate to the directory. Copy the address. In Git Bash, type `cd ` (note the space after cd) and then paste the address (SHIFT+INS). If your path has spaces in it, you'll need to add double quotes around it.  
     2.  Option B: within Git Bash, navigate to your directory using `cd ` command.

3. In Github, go back to "Code" in the top menu bar.
4. Click the green "<> Code" button in the upper right. Make sure you are on the **HTTPS** tab (we haven't set up SSH); copy the URL to your clipboard.
5. In Git Bash, type `git clone ` (note the space after clone) and then paste (SHIFT+INS) the URL. 
6. Navgiate into to that repository by typing `cd <your_repo_name>`. If you're in Git Bash, you'll notice `(main)` appear after the filepath. That's a good sign that you're in a git repository.

## Practice!
Now, we are going to practice a few basic commands in git.

### Make some local changes
1. Open up your README file in your preferred editor (VS Code, Notepad, vim, etc.).
2. Add the following line: `This is a sample README for WIDS DC 2024. In it, I will write some simple python code, edit it, and track changes.`
3. Add this change to the staging area by going back to Git Bash, typing `git add README.md`. (you can always check the status of any file you've edited by typing `git status`)
4. Type `git commit -m "modify readme"`.
5. Create a new file called `hello.py`. Edit that file to add the python code `print("hello world")`. Save.
6. Commit this change by going back to Git Bash, typing `git add hello.py` (pro tip: most terminals/Git Bash have tab complete) then `git commit -m "create hello.py; print hello world"`
7. Check your log! What have you done so far? Type `git log --oneline`. The oneline flag will make it display each commit on one line which makes it easier to read.
8. Add another line to your README, `I am learning git!`. Make sure there is a blank line between your previous text and this new line. Save!
9. Before staging and committing that file, check what changed by typing `git diff README.md`.
10. Then, add the file to the staging area and the commit it with a helpful message.

### Push your changes to the remote repo
1. Type `git push`. Enter any credentials you are prompted for.
2. Navigate to the remote repository in your browser (there will be a link the second-to-last line in the output after you push. Check to make sure your changes are there!

### Make a new branch
Now, create a new branch to change the code in our `hello.py` file.

1. Create a new branch by typing `git branch change_hello_msg`. Switch to that branch using `git checkout change_hello_msg`. (Pro tip: do this in one command using `git checkout -b change_hello_msg`. This will create the new branch and immediately switch to that branch.)
3. Edit the hello.py file to change "world" to "WiDS". Save!
4. Add and commit the file.
5. Switch back to your main branch by typing `git checkout main`. Check the file again - has the text changed?
6. Merge your changes into the main branch by typing `git merge change_hello_msg`.
7. Check the log by typing `git log --oneline`. You should see each commit on main as well as the commits from the new branch since we've now merged them in.
8. Push your changes to the remote repository and check them out in Github!
9. Navigate to the `hello.py` file in Github, then click "History" in the upper right. Click on the title of the most recent commit to see exactly what changed.
