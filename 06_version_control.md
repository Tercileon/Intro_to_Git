<a href="https://github.com/Tercileon/Intro_to_Git/blob/master/00-Table-of-Contents.md" > Return to TOC </a>

---

## Introduction to Version Control

---

A **version control system** is a tool that lets you track the history and attribution of your project files over time which helps with project management and keeping track of development with multiple contributors.  Modern version control systems help teams work simultaneously by giving each developer his or her own sandbox and preventing their work in progress from conflicting. While also providing a mechanism to merge changes and synchronize work.

**Distributed version control systems**, like Git, give each developer their own clone of the repository which also tracks the project's history.

#### ![](/assets/git1.png)

#### Push

The **push **command indicates to Git where your repository is located and allows you to **push **those changes when you're ready. Push creates a local branch in the destination repository. Which can then be inspected and merged into the master. Git will only allow a **fast-forward** merge.  In other words, the commit history of your branch first needs to match the history of the master branch.

> **git push -u \[remote repo name\] \[branch name\]**
>
> \(The **-u** tells Git to remember the parameters.  So that next time we can simply run **git push**.\)

#### Pull

The **pull command **allows us to check for changes in the repository and pull down any new changes and update your local repository or branch.

> **git pull \[remote repo name\] \[branch name\]**

When you open a _**pull request**_**,** you’re proposing your changes and requesting that someone review and pull in your contribution and merge them into their branch. Pull requests show differences \(_**diffs**_\) of the content from both branches.

As soon as you make a commit, you can open a pull request and start a discussion, even before the code is finished.

#### Fetch

If you want to review new code in a repository before merging it with your own you can use **Fetch**. This creates a **remote branch** in your repository that you are able to inspect for changes.

> **git fetch \[remote repo name\] \[branch name\]**

#### Differences

The **git diff** command allows you to see what changes have been made to thd repository since your last commit.

> **git diff --no-index \[--options\] \[--\] -&lt;path&gt;...\]**
>
> This command is used to compare two paths on the filesystem. **--no-index **can be imitted when running the command in a working tree controlled by Git and at least one of the paths points outside the working tree.
>
> **git diff HEAD**
>
> \(**HEAD **is a pointer that holds your position within all your different commits.  By default **HEAD **points to the same place as your most recent commit, so it can be used as a quick way to reference that commit without having to look up the SHA.\)

**Git diff** can also be used to see changes in files that are in the staging area.

> **git diff --staged**

#### Reset

In order to remove files from the staging area use **git reset.**

> **git reset \[file name or file path\]**

To revert files/directories back to a previous commit use **checkout.**

> **git checkout -- \[file or directory\]**
>
> \(The **"--"** signify's there are no more option after the command.\)
>
> **git checkout b7119f2 path/to/file path/to/file**
>
> \(Use the SHA hash if you would like to specify a previous commit\)

# Merge

Once everyone has reviewed the new code and you are ready to commit those changes to the master repository, you can use Merge to save the  new feratures/updated code to the master repository. Merging is a non-destructive operation.  The existing branches are not changed in any way.  The new code will only be added on top of the master.

> **git merge \[remote repo name \(master\)\] \[branch name\]**

##### More on Syncing: [https://www.atlassian.com/git/tutorials/syncing](https://www.atlassian.com/git/tutorials/syncing)

After merging your branch to the master, you can delete your local branch by using:

> **git branch -d \[branch name\]**
>
> \(This will only work after a merge has been made.  To force a delete use **--force** \(**-f**\) or **-D**, which combines **-d** and **-f**.\)

---

# **Common workflow when working with git**
Now that we've gone over the basics for git you may be overwhelmed. That is ok, as you use git every day you will become more familiar with the commands and you'll realize where and why it is so advantageous. Now we can go through a scenario and you can see how quick and easy git can be when you get used to it.


### **Create your branch that you're working on**
> git branch &lt;your branch name>

### **Display all branches to see which branch you're currently on**
> git branch

### **Switch to your branch**
> git checkout &lt;your branch name>  
> git branch  

> git status  
> git add .  
> git commit -m "changed files from my branch"
### **We haven't affected our local master branch or our remote repository**

### **Push your branch to the remote**
> git push -u origin &lt;your branch name>  
> git branch -a

## **Merge your branch with master**
### **Checkout to master**
> git checkout master  
> git pull origin master  
### **Check branches that are merged so far**
> git branch --merged
### **Changes are merged**
> git merge &lt;your branch name>  
### **Push to remote master**
> git push origin master

### **If feature you're working on is done you can delete branch or keep it, that is up to your dev environment**
> git branch -d &lt;your branch name>  
> git branch -a  
### **Deleted locally, but now need to delete remote**
> git push origin --delete &lt;your branch name>

---
<a href="https://github.com/Tercileon/Intro_to_Git/blob/master/07_resources.md" > Continue to Next Topic </a>

---

