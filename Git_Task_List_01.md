# Part 1: Introduction to Version Control and Git

## Task 1: Install and  Configure Git

1. Configure Git with your username and email:

```
git config --global user.name "Mayank Dudhatra"

git config --global user.email "mayankdudhatracg@gmail.com" 
```

```
**Explaination**:- git config: This is the command to configure Git settings.

--global: This applies the configuration globally to all repositories on your system.

user.name: This is the key to configure the username.

user.email: This is the Key to Configure the email.
```


2. View Your Git configure
```
git config --list
```
```
**Explaination** :- This Command List all the Git Configuration.
```

## Task 2: Initialize a Repository

1. Create a new project and navigate to it.
```
mkdir MyProject

cd MyProject
```
```
**Explaination** :- mkdir: This is the Command is used to Create New Folder.

cd: This is the Command is used to move into any Folder.
```

2. Initialize it as a Git repository:
```
git init
```
```
**Explaination :- git init: This Initialize the current folder as Repository. After Initialize, a hidden .git folder apper in the ddirectory. 
```
## Task 3: Create a File and Make Multiple Commits

1. Create a new file and add content:
```
echo "My First Project" > README.md
```
2. Stage the file:
```
git add README.md
```
3. Commit the file:
```
git commit -m "Initial commit: Added README.md"
```
4. Make changes to the file:
```
echo "Added a description" >> README.md
```
5. Stage and commit the changes:
git add README.md
```
git commit -m "Updated README with a description"
```
```
Explaination :- echo: This command creates a new file named README.md and writes the text "My First Project" into it. 

git add . : This Command Stage all chnages in the directory and Track all the files.

git commit: This Command save a screenshot of the current state of your Repository.
-m : Allow you to add commit message .

>>: Unlike >, this appends the text to the file without overwriting its existing content.

In last after new changes , new Commit is created. 
```

## Task 4: Check Status and Log

1. Check the repository’s current status:
```
git status
```
2. View commit history in detail:
```
git log --oneline --graph --decorate
```
Example Output:
```
* 2f8d6a2 (HEAD -> main) Updated README with a description
* d3c4b21 Initial commit: Added README.md
```
```
Explaination :- git status: This command displays the state of the working directory and the staging area.


git log: This Command display the commit history of this Repository.
--oneline: condess each command into single line for readability.
--graph: Display the Graphical represenstation of of the branch srtucture and merge in the commit history
--decorate: Adds Labels,to indicate branches, tags and reference.
```
## Task 5: Create and Clone a Repository

1. Create a repository on GitHub named example-repo.

2. Clone it locally:
```
git clone http://codinggita.com/example-repo
```
```
Explaination :- git clone: This command copies the repository from the Remote server to Local Machine .
```

## Task 6: Understanding the Git Workflow
- Example Workflow:

i. Make changes to a file in the working directory:
```
echo "Workflow example" > workflow.md
```
ii. Stage the File:
```
git add workflow.md 
```

iii. Commit the file to the repository:
```
git commit -m "Added workflow example"
```
```
Explaination :- echo:  Output the text "Workflow Example" to the file.
>: Redirect the Output to the specified line.

git add . : This Command Stage all chnages in the directory and Track all the files.

git commit: This Command save a screenshot of the current state of your Repository.
-m : Allow you to add commit message .
```


# Part 2: Working with Repositories

## Task 7: Branching and Merging

1. Create a new branch for a feature:
```
git branch feature-login
git checkout feature-login
```

Or Use:
```
git checkout -b feature-login
```

2. Add a new file and commit changes:
```
echo "Login Page" > login.html
git add login.html
git commit -m "Added login page"
```
3. Merge the feature branch into main:
```
git checkout main
git merge feature-login
```
```
Explaination :- git branch <name>: This Command create a new branch .

git checkout <name>: This command switch the branc.

git checkout -b <name>: This Command create new branch and switch into it in one step.

echo "Text" > <file name>: This command create a new file and write text into it.

git add . : This Command Stage all chnages in the directory and Track all the files.

git commit: This Command save a screenshot of the current state of your Repository.
-m : Allow you to add commit message .

git checkout main: this com switches to main branch.

git merge feature-login: This command merge the feature-login to main brach. 
```

## Task 8: Handling Merge Conflicts

1. Create two branches:
```
git branch branch-A
git branch branch-B
```
2. Modify the same line in README.md in both branches.

3. Merge branch-A into main:
```
git checkout main
git merge branch-A
```
4. Attempt to merge branch-B into main (this will cause a conflict):
```
git merge branch-B 
```
5. Resolve the conflict manually in README.md, then:
```
git add README.md
git commit -m "Resolved merge conflict between branch-A and branch-B"
```
```
Explaination :- git brach <branch name>: This Command Create a new Branch into main branch.

```
## Task 9: Renaming and Deleting Branches

1. Rename a branch:
```
git branch -m old-branch-name new-branch-name
```
2. Delete a branch:
```
git branch -d feature-login
```
```
Explaination :- git branch -m <old-name> <new-name>: This Command Rename the branch.

git branch -d <branch-name>: This command Delete the branch.
```

# Part 3: Advanced Git Operations

## Task 10: Using Git Stash

1. Make changes to a file but don’t commit:  
   ```bash
   echo "Temporary work" >> temp.md
   ```
2. Stash the changes:  
   ```bash
   git stash
   ```
3. View stashed changes:  
   ```bash
   git stash list
   ```
4. Apply the stashed changes:  
   ```bash
   git stash apply
   ```
5. Drop the stash after applying:  
   ```bash
   git stash drop
   ```

   ```
   Explaination :- echo:  Output the text "Workflow Example" to the file.
   >>: Unlike >, this appends the text to the file without overwriting its existing content.

   git stash: Temporarily saves (or stashes) the changes made in the working directory and staging area, then reverts the files to the last committed state.

   git stash list: Displays a list of all stashes in your repository. Each stash is identified by an index 

   git stash apply: Applies the most recent stash (stash@{0}) back to the working directory without removing it from the stash list.

   git stash drop: Removes the most recent stash (stash@{0}) from the stash list.
   ```

## Task 11: Rewriting History with Interactive Rebase

1. Create multiple commits:
```
echo "Commit 1" > file1.txt && git add file1.txt && git commit -m "Commit 1"
echo "Commit 2" > file2.txt && git add file2.txt && git commit -m "Commit 2"
echo "Commit 3" > file3.txt && git add file3.txt && git commit -m "Commit 3"
```
2. Squash commits into one:
```
git rebase -i HEAD~3
```

```
Explaination :- echo "Text" > <file-name>: echo create a file and write Text into it.
git add <file-name>: Stage the file to be commited. 
git commit -m "message": Create the first commit with message.

git rebase -i: The -i flag stand for Interactive rebaseb,which allows you to manipulate commits.
HEAD~3: HEAD~3 means 3 commits before the current commit.
```
## Task 12: Cherry-Picking Commits

1. Create a new branch:
```
git checkout -b cherry-pick-example
```
2. Cherry-pick a specific commit from another branch:
```
git cherry-pick <commit-hash>
```
```
Explaination :- This Command Create a new branch and switch into it (IN one Step).

git cherry-pick <commit-hash>: This command takes the changes introduced by the commit with the specified <commit-hash> and applies those changes to your current working branch as a new commit. 
```

## Task 13: Tagging Commits

1. Tag the current commit:
```
git tag -a v1.0 -m "Version 1.0 release"
```
2. Push the tag to the remote repository:
```
git push origin v1.0
```
```
Explaination :- git tag: This command creates a tag on the current commit.
-a v1.0: The -a flag specifies that you`re creatinf an annotated tag .The v1.0 is the name of the tag.

-m "Version 1.0 release": This provides a message for the tag.

git push origin v1.0: This command pushes the tag (v1.0) to the remote repository.
```

## Task 14: Working with Remote Repositories

1. Add a remote repository:
```
git remote add origin <repository-url>
```
2. Push your changes to the remote repository:
```
git push origin main
```
```
Explaination :- git remote add origin: This command adds a remote repository to your local Git repository. The remote repository is where your code can be pushed or pulled from.

git push origin main: This command pushes your local changes to the remote repository.
```

## Task 15: Forking and Contributing

1. Fork a repository on GitHub.

2. Clone the fork locally:
```
git clone <forked-repo-url>
```
3. Create a new branch, make changes, and push:
```
git checkout -b fix-typo
echo "Typo fixed" >> README.md
git add README.md
git commit -m "Fixed a typo"
git push origin fix-typo
```
4. Open a pull request on GitHub.
```
Explaination :- Fork: Forking a repository on GitHub creates a copy of someone else's repository under your own GitHub account.

git clone <forked-repo-url>: This command clones your forked repository from GitHub to your local machine. 

git checkout -b <branch-name> : This command creates a new branch and switches to it.

echo "Typo Fixed" >> README.md: This command adds the text "Typo fixed" to the end of the README.md file.

git add README.md: Stages the README.md file for committ.

git commit -m "Fixed a typo": Commits the staged changes, with a message.

git push origin fix-typo: This command pushes fix-typo branch and its changes the fork on GitHub.


```

# Part 4: Additional Practice

## Task 16: Simulate Team Collaboration

1. Create a repository and share it with a friend.
2. Both make changes to the same file simultaneously.
3. Practice resolving merge conflicts and pushing changes.
```
Explaination :-
```

## Task 17: Git Ignore

1. Create a .gitignore file:
```
echo "node_modules/" > .gitignore
```
2. Add files and ensure ignored files are not staged:
```
git add .
```
```
Explaination :- echo "node_modules/" > .gitignore: This command creates a .gitignore file and adds the line node_modules/ to it.

git add .: The command stages all changes in the current directory for commit.
```







