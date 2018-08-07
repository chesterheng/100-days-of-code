# 1. Create a repository with files and push changes to a remote repository

## Scenario: I have a folder on my computer locally and want to push it to a Github repository
* Create a simple html text file 
* Create the repository on Github by Clicking New
* **git init** [start using git here]
* **git add .** [add all files to this commit]
* **git commit -m "first commit"** [track these changes]
* **git remote add origin git@github.com:{YourAcctName}/test.git** [take the changes and enforce them elsewhere]
* **git push -u origin master

# 2. Work around changes in a remote repository

## Scenario: I want to take an existing repository of mine on Github and bring it down to my computer locally
* Create and/or Go to folder where you want repositories to be locally:
* mkdir ~/cloned-repos
* cd ~/cloned-repos
* Copy to clipboard the SSH clone URL to use with git clone
* **git clone git@github.com:{YourAcctName}/test.git**

## Scenario: I have cloned a repo, made some changes locally, and I want to push those changes to the remote repo
* **git remote -v** [Check existing remote sources]
* **git remote add** origin git@github.com:{YourAcctName}/test.git [Add your target remote path to the remote sources]
* **git remote -v** [Verify it's been added]
The Takeaway: You've given a nickname to where to push changes not just locally, but elsewhere. You've named it origin.
* **Run git add .**
* **Run git commit** [Go through the normal routine to commit changes]
* **git push -u origin master** [Push "upstream", that's what the option -u stands for]
The Takeaway:You've designated your master branch to be pushed upstream to the remote nicknamed origin

## Scenario: I have committed some changes to my repository, but it was a mistake and I want to go back.
The most common options are “soft” and “hard” resets. The former keeps your changes, but rolls back the commit status to say that you've got changes to commit. The latter completely erases your changes and the commits.
* Find the commit hash on Github
* Run git reset --hard <hashcode_here>
* The soft reset is git reset --soft <hashcode_here>
* Note: git push may require --force

## Scenario: I want to bring down changes from the remote repository into my local copy.
It depends on whether you have local changes. Remember you might have local edits not pushed.
git pull does a git fetch followed by a git merge
So if you want to see the differences before merging then:
Run git fetch (sync with remotes)
Run git diff origin/master -otherwise-
Run git pull (resolve merge conflicts if they arise)
