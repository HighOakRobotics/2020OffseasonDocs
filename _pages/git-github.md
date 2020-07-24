---
permalink: /git-github
title: Setting Up Git and Github
---

### Download and Install [Git](https://git-scm.com/downloads)
* Keep everything as default in the installer (if you don’t like Vim as the default editor you can set it to Nano; it will only show up when you resolve merge conflicts in the terminal)   
* You MUST restart Android Studio after installing Git in order for its Git integrations to work

### Create a [GitHub Account](https://github.com/join) 
* (it's free of charge)    
* If you're a student, the [GitHub Student Developer Pack](https://education.github.com/pack) is a good way to get free things   
  
### Set GitHub Credentials in Git
* Go to the Terminal (on Windows this is either GitBash or Powershell, on Mac or Linux it's Terminal)
* once you're there run the following commands:   
  * `git config --global user.name <your GitHub username>`   
  * `git config --global user.email <the email you signed up to GitHub with>`   
* You can confirm these commands worked by typing `git config --global user.name` (user.email for email)

### Creating an FTC Repository
* Go to Git Bash
* Navigate to an empty folder (this will store your repo)
  * `cd <path to folder>`
* `git init`
* `git remote add upstream <FTC repo link>` (at the moment it's https://github.com/FIRST-Tech-Challenge/SkyStone)
* `git pull upstream master`
* Create an empty GitHub repository from the website interface (do NOT initialize it with a README, LICENSE, or gitignore)
* `git remote add origin <your own empty repo link>`
* `git push -u origin master`

You would repeat this process (aside from git init and creating a new GitHub repo) whenever FTC releases an official update to their repo   
To remove a remote, use `git remote rm <remote-name>` so you can repeat the process again without naming conflicts.  
You could also skip creating new remotes altogether but it could get confusing (especially when FTC inevitably moves repos)  

### Cloning an existing Repository
A repository (repo) is the remote storage space for your code   
Cloning a repo downloads the repo onto your computer and sets up its configuration for use with git   
#### Steps:
* Open Android Studio and select "Get from Version Control"  
* In the dropdown menu, select "Git"  
* Paste the repository's URL you want to download in the "URL" blank  
* Choose an empty folder to clone into for "Directory"  
* Click "Clone"  
* Once it finishes, hit "OK".  
* If Android Studio tells you a project file is detected, open it
* If Android Studio asks you to create a project from new or existing sources, select existing
* Click through any other prompts leaving everything as is

#### Common problems:
* If your firewall activates, let Android Studio through on both public and private networks
* If the build fails: 
  * try closing the project, then go to Configure > SDK Manager
  * SDK Platforms tab - make sure Show Package Details is checked at the bottom right
  * Android 9.0 (Pie) - Check off and download Android SDK Platform 28 and Sources for Android 28, then reopen the project
  
### Git Usage
Run Git commands through the “terminal” window in Android Studio
Make sure you’re on the right branch as well as under the right folder

* To retrieve code from GitHub's remote repositories, use `git pull`
  * it fetches all of the code from the remote repository (i.e. the code stored on GitHub), and merges it into your local repo (i.e. the folder on your computer) 
  * this is how you pull changes that other people have made onto your computer
  * you don't have to do this when you first download a repo - it is downloaded up to date.
* To push your changes from your local computer to GitHub:
  * First use `git add <file path>` - this will prepare the file in question to be committed as a definite change
    * if you want to add every file currently changed, use `git add *`
  * Next use `git commit -am <commit name>` - this will make the changes on your local repository official.
  * Lastly use `git push` to transfer your local changes to the remote GitHub repository.
    * you can push more than one git commit at a time; git will maintain the order accordingly.
    
### Branching
Branches allow multiple versions of the code to coexist at once, making team development more streamlined. For example, I can have the master branch for the official code, and another branch called auto for development
* To switch to an existing branch, run: `git checkout <branch_name>`. You may need to pull after switching
* To create a new branch (from the current branch) and switch to it, run: `git checkout -b <branch_name>`
* The master branch is usually restricted from direct changes, as it is meant for code that is tested and absolutely works. For this reason, changes are made to master through merging into it from other branches.

### Merging
GitHub has its own built-in feature to make merging branches team-friendly - Pull Requests.
* Pull Requests allow us to view changes and request reviews before going through with a merge
* You should always have a trusted administrator review your Pull Request and merge it
* If there are merge conflicts, contact an admin for help resolving them

#### What happens if I forgot to push my changes but want to pull in new changes? (there are changes to both pull and push)
* First, once your changes are complete, commit them (don’t push)
* Then run a special pull: `git pull --rebase`
  * Reorders the commits to avoid merging
* Sometimes merging is unavoidable.
  * If Git is able to automatically merge, then we’re good
  * Otherwise, if there are conflicts, contact an admin to get help resolving them - [this page](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/resolving-a-merge-conflict-using-the-command-line) has information about resolving merge conflicts
