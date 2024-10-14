# Using Tools for Effective Open Science Collaboration: Github.
For participants in the WSDS Short Course, Using Tools for Effective Open Science Collaboration: Github.

## Setup
Before the workshop on October 16, following the instructions below.

### Install Git
1. Follow the [instructions for your operating system](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).
   1. If you already have anaconda installed, you can install git using conda: `conda install git`
3. Verify that Git is installed:

| Windows | Mac | Linux |
| ------ | ---- | ----- |
|	Open the Git Bash application (Search > Type “Git Bash” > Click the Git Bash application). | Open a Terminal (Spotlight > Type “terminal” > Click the Terminal application). | Open a Terminal (CTRL+ALT+T). |
| In the new Git Bash window, type `git --version`. | In the new Terminal window, type `git --version`. | In the new Terminal window, type `git --version`. |
| If Git Bash prints the version number (e.g., git version 2.36.1.windows.1), then you’re good to go! |	If the terminal prints the version number (e.g., git version 2.36.1), then you’re good to go! |	If the terminal prints the version number (e.g., git version 2.36.1) | then you’re good to go!

_Example output:_

![image](https://github.com/juliabuffinton/wids_2024/assets/39072451/3de68dc3-b202-4602-a8ff-026af485460b)

### Make a Github Account
1. Navigate to [GitHub.com](https://github.com/).
2. Click the "Sign up" button in the upper right corner. (If you already have an account, click the "Sign in" button.)
3. Complete the required fields and then click the "Create account" button.
4. Make sure you are signed in for the exercises.

### Create a Personal Access Token
1. From the Github home page, click on your profile picture in the upper right. Scroll down to settings at the bottom.
2. On that page, scroll down to the bottom and click on "Developer Settings" in the left menu.
3. Click on "Personal Access Tokens" then "Tokens (classic)".
4. In the upper right, click on "Generate a new token (classic)". You may be prompted to complete multi-factor authentication before moving onto the next page.
5. Give it a descriptive note, then check the "repo" box. You do not need to change the default expiration, unless you are planning to use it beyond this workshop. You can always generate more, you just have to update any scripts that might reference it.
6. Scroll to the bottom and click the green "Generate token" button!
7. When your token is generated, SAVE IT SOMEWHERE. You will not see it again, but you will need it to interact with the remote repository.

You can use a credential manager so you don't have to add your token every time you push or pull. For details on how to do that, [check out this page](https://docs.github.com/en/get-started/getting-started-with-git/about-remote-repositories#cloning-with-https-urls).

**Preferred method**: [Set up SSH!](https://docs.github.com/en/authentication/connecting-to-github-with-ssh) 

### Final Configuration

1. Open up Git Bash (Windows) or terminal (Mac/Linux). Type the following commands (press enter between each) to set your name and email. Change "Your Name" and "Your Email" to your actual name and email, or whatever you would like displayed alongside your commits.

`git config --global user.name "Your Name"`

`git config --global user.email "Your Email"`

2. Change your default branch name (more on that later!) to "main." This will ensure compatibility with GitHub. The below command will do this for all future-created git repositories on your machine because you're using the `--global` flag.

`git config --global init.defaultBranch main`

3. Automatically set up a remote tracking branch when you create a new branch locally (more on this later, too!). This will simplify the process of pushing changes to a remote repository.

`git config --global push.autoSetupRemote true`

4. Check that everything you just did "stuck" by examining your configuration for the items above.

`git config --list`
