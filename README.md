# Git-And-Github

## What is Git?  
Git is a popular version control system. 

It is used for:

Tracking code changes  
Tracking who made changes  
Coding collaboration

## What does Git do?
Manage projects with Repositories  
Clone a project to work on a local copy  
Control and track changes with Staging and Committing  
Branch and Merge to allow for work on different parts and versions of a project  
Pull the latest version of the project to a local copy  
Push local updates to the main project

## What is GitHub?
Git is not the same as GitHub.  
GitHub makes tools that use Git.  
GitHub is the largest host of source code in the world, and has been owned by Microsoft since 2018.

## Git Install  
You can download Git for free from the following website: https://www.git-scm.com/

For Windows, you can use Git bash, which comes included in Git for Windows.

## Configure Git  
Now let Git know who you are. This is important for version control systems, as each Git commit uses this information:  

`git config --global user.name "w3schools-test"  `  
`git config --global user.email "test@w3schools.com"`

Change the user name and e-mail address to your own. You will probably also want to use this when registering to GitHub later on.

## Creating Git Folder
Now, let's create a new folder for our project: 

`mkdir myproject  `  
`cd myproject`

mkdir makes a new directory.

cd changes the current working directory.

Note: If you already have a folder/directory you would like to use for Git:

Navigate to it in command line, or open it in your file explorer, right-click and select "Git Bash here"

## Or

## Initialize Git  
Once you have navigated to the correct folder, you can initialize Git on that folder:  

`git init `  
```
Initialized empty Git repository in /Users/user/myproject/.git/
```

You just created your first Git Repository!

Note: Git now knows that it should watch the folder you initiated it on.

Git creates a hidden folder to keep track of changes.

## list the files in our current working directory:  

`ls`  
```
index.html
```

ls will list the files in the directory. We can see that index.html is there.

Then we check the Git status and see if it is a part of our repo:

`git status`  
```
On branch master

No commits yet

Untracked files:
  (use "git add ..." to include in what will be committed)
    index.html

nothing added to commit but untracked files present (use "git add" to track) 

```

Now Git is aware of the file, but has not added it to our repository!

Files in your Git repository folder can be in one of 2 states:

Tracked - files that Git knows about and are added to the repository  
Untracked - files that are in your working directory, but not added to the repository  
 When you first add files to an empty repository, they are all untracked. To get Git to track them, you need to stage them, or add them to the staging environment.
 
 ## Git Staging Environment
One of the core functions of Git is the concepts of the Staging Environment, and the Commit.

As you are working, you may be adding, editing and removing files. But whenever you hit a milestone or finish a part of the work, you should add the files to a Staging Environment.

Staged files are files that are ready to be committed to the repository you are working on. You will learn more about `commit` shortly.

For now, we are done working with `index.html.` So we can add it to the Staging Environment:  
`git add index.html`  
The file should be Staged. Let's check the status::  
`git status`  
```
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached ..." to unstage)
    new file: index.html

```  
Now the file has been added to the Staging Environment.

## Git Add More than One File

Now add all files in the current directory to the Staging Environment:  
`git add --all`

Using --all instead of individual filenames will stage all changes (new, modified, and deleted) files.

`git status`  
```
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached ..." to unstage)
        new file:   README.md
        new file:   bluestyle.css
        new file:   index.html
```
Now all 3 files are added to the Staging Environment, and we are ready to do our first commit.  
Note: The shorthand command for git add --all is git add -A

## Git Commit  

Since we have finished our work, we are ready move from stage to commit for our repo.  

Adding commits keep track of our progress and changes as we work. Git considers each commit change point or "save point". It is a point in the project you can go back to if you find a bug, or want to make a change.

When we commit, we should always include a message.

By adding clear messages to each commit, it is easy for yourself (and others) to see what has changed and when.

`git commit -m "First release of Hello World!"`

```
[master (root-commit) 221ec6e] First release of Hello World!
 3 files changed, 26 insertions(+)
 create mode 100644 README.md
 create mode 100644 bluestyle.css
 create mode 100644 index.html
 ```
 The commit command performs a commit, and the -m "message" adds a message.  
 The Staging Environment has been committed to our repo, with the message:
"First release of Hello World!"

## Git Commit Log:  
To view the history of commits for a repository, you can use the log command:  
`git log`  
```
commit 09f4acd3f8836b7f6fc44ad9e012f82faf861803 (HEAD -> master)
Author: w3schools-test 
Date:   Fri Mar 26 09:35:54 2021 +0100

    Updated index.html with a new line

commit 221ec6e10aeedbfd02b85264087cd9adc18e4b26
Author: w3schools-test 
Date:   Fri Mar 26 09:13:07 2021 +0100

    First release of Hello World!
```

## Git Help  
If you are having trouble remembering commands or options for commands, you can use Git help.  
`git command -help`  
&  
` git help --all`  
Note: If you find yourself stuck in the list view, SHIFT + G to jump the end of the list, then q to exit the view.  

## Git Branch  
Working with Git Branches  
In Git, a branch is a new/separate version of the main repository.  
Let's say you have a large project, and you need to update the design on it.

Branches allow you to work on different parts of a project without impacting the main branch.

When the work is complete, a branch can be merged with the main project.

You can even switch between branches and work on different projects without them interfering with each other.

Branching in Git is very lightweight and fast!  

## New Git Branch

We are working in our local repository, and we do not want to disturb or possibly wreck the main project.

So we create a new `branch`:  
`git branch hello-world-images`  
Now we created a new branch called "hello-world-images"

Let's confirm that we have created a new branch:  
`git branch`  
```
 hello-world-images
* master
```
We can see the new branch with the name "hello-world-images", but the * beside master specifies that we are currently on that branch.

checkout is the command used to check out a branch. Moving us from the current branch, to the one specified at the end of the command:  
`git checkout hello-world-images`  
```
Switched to branch 'hello-world-images'
```
Now we have moved our current workspace from the master branch, to the new branch

Open your favourite editor and make some changes.  
added an image (img_hello_world.jpg) to the working folder and a line of code in the index.html file  
We have made changes to a file and added a new file in the working directory (same directory as the main branch).

Now check the status of the current branch:  
`git status`  
```
On branch hello-world-images
Changes not staged for commit:
  (use "git add ..." to update what will be committed)
  (use "git restore ..." to discard changes in working directory)
        modified:   index.html

Untracked files:
  (use "git add ..." to include in what will be committed)
        img_hello_world.jpg

no changes added to commit (use "git add" and/or "git commit -a")
```  
So let's go through what happens here:

There are changes to our index.html, but the file is not staged for commit  
img_hello_world.jpg is not tracked  
So we need to add both files to the Staging Environment for this branch:  
`git add --all`  
Using --all instead of individual filenames will Stage all changed (new, modified, and deleted) files.

Check the status of the branch:  
`git status`  
```
On branch hello-world-images
Changes to be committed:
  (use "git restore --staged ..." to unstage)
    new file: img_hello_world.jpg
    modified: index.html
```
We are happy with our changes. So we will commit them to the branch:  

Going Further is difficult so checkout another time when you have free time.

# GitHub Account

1. GitHub Account  
2. Create a Repository on GitHub  
3.  Push Local Repository to GitHub:  
Since we have already set up a local Git repo, we are going to push that to GitHub:  
Copy the URL, or click the clipboard marked in the image above.

Now paste it the following command:  
`git remote add origin https://github.com/Roxhitttt/Git-And-Github.git`  
git remote add origin URL specifies that you are adding a remote repository, with the specified URL, as an origin to your local Git repo.  
Now we are going to push our master branch to the origin url, and set it as the default remote branch:  
`git push --set-upstream origin master`  
```
Enumerating objects: 22, done.
Counting objects: 100% (22/22), done.
Delta compression using up to 16 threads
Compressing objects: 100% (22/22), done.
Writing objects: 100% (22/22), 92.96 KiB | 23.24 MiB/s, done.
Total 22 (delta 11), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (11/11), done.
To https://github.com/w3schools-test/hello-world.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.
```


