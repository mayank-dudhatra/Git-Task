### **Part 1: Git Basics**

#### **Task 1: Install and Configure Git**
1. Install Git from [git-scm.com](https://git-scm.com/).  

2. Configure your global Git settings:  
   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "your-email@example.com"
   ```
3. Verify the configuration:  
   ```bash
   git config --list
   ```
```
Explaination :-  git config: This is the command to configure Git settings.

--global: This applies the configuration globally to all repositories on your system.

user.name: This is the key to configure the username.

user.email: This is the Key to Configure the email.
```

#### **Task 2: Initialize a Repository**
1. Create a directory and initialize it as a Git repository:  
   ```bash
   mkdir MyProject
   cd MyProject
   git init
   ```
   - **Purpose**: Initializes a `.git` folder to track changes.

---
```
Explaination :- mkdir: This is the Command is used to Create New Folder.

cd: This is the Command is used to move into any Folder.

git init: This Initialize the current folder as Repository. After Initialize, a hidden .git folder apper in the directory. 
```

### **Part 2: Basic Workflow**

#### **Task 3: Creating and Committing Files**
1. Create a file:  
   ```bash
   echo "Hello Git" > file1.txt
   ```
2. Stage and commit the file:  
   ```bash
   git add file1.txt
   git commit -m "Initial commit: Added file1.txt"
   ```
   ```
   Explaination :-  echo "Hello Git" > file1.txt : This command creates a new file named file1.txt and writes the text "Hello Git" into it. 

   git add . : This Command Stage all chnages in the directory and Track all the files.

   git commit: This Command save a screenshot of the current state of your Repository.
   -m : Allow you to add commit message .

   ```

#### **Task 4: Viewing Changes**
1. Modify the file:  
   ```bash
   echo "Git is awesome!" >> file1.txt
   ```
2. Check file status and differences:  
   ```bash
   git status
   git diff
   ```
   ```
   Explaination :- >>: Unlike >, this appends the text to the file without overwriting its existing content.

   git status: This command shows the current state of your working directory and staging area.

   git diff: This command displays the differences between the working directory and the staging area.

#### **Task 5: Undoing Changes**
1. Unstage a staged file:  
   ```bash
   git reset file1.txt
   ```
2. Discard uncommitted changes:  
   ```bash
   git checkout -- file1.txt
   ```
   ```
   Explaination :- git reset: This command is used to unstage a file that was previously added to the staging area using git add.

   git checkout -- : This command is used to discard uncommitted changes in a specific file and restore it to its last committed state.
   ```

---

### **Part 3: Branching and Merging**

#### **Task 6: Branch Management**
1. Create a branch and switch to it:  
   ```bash
   git checkout -b feature-branch
   ```
2. List branches:  
   ```bash
   git branch
   ```
3. Rename a branch:  
   ```bash
   git branch -m feature-branch feature-enhanced
   ```
   ```
   Explaination :- git checkout -b <name>: This Command create new branch and switch into it in one step.
   
   git branch: This command lists all the branches in your Git repository.

   git branch <old name> <new name>: This command rename an exsisting branch.
   ```
   

#### **Task 7: Merging Branches**
1. Merge `feature-enhanced` into `main`:  
   ```bash
   git checkout main
   git merge feature-enhanced
   ```
   ```
   git checkout <branch name>: This command sitwch from current branch to another branch.

   git merge: The git merge command is used to combine the work of one branch into another.
   ```

#### **Task 8: Handling Merge Conflicts**
1. Create two conflicting branches and resolve a conflict manually:  
   ```bash
   git merge <branch-name>
   ```
2. Use:  
   ```bash
   git add <resolved-file>
   git commit
   ```
   ```
   Expalination :- git merge <branch-name>: Merges the specified branch into the current branch. If there are conflicting changes, Git marks the files in conflict for manual resolution.

   git add <resolved-file>: Stages the resolved file after conflicts are resolved manually.

   git commit: Creates a new commit recording the resolution of the conflict.
   ```

---

### **Part 4: Remote Repositories**

#### **Task 9: Remote Setup**
1. Add a remote repository:  
   ```bash
   git remote add origin https://github.com/your-username/repo.git
   ```
2. Verify the remote:  
   ```bash
   git remote -v
   ```
   ```
   Explaination :- git remote add origin: This command adds a remote repository to your local Git repository. The remote repository is where your code can be pushed or pulled from.

   git remote: Lists all remote repositories linked to your local repository.
   -v: Displays detailed information about each remote repository, including the URLs used for fetching and pushing.
   ```
#### **Task 10: Push and Pull**
1. Push changes to the remote repository:  
   ```bash
   git push -u origin main
   ```
2. Pull changes from the remote:  
   ```bash
   git pull origin main
   ```
   ```
   Explaination :- git push: Sends your local changes to the remote repository.
   -u: This  is the shorthand for --set-upstream.
   origin: The name of the remote repository.
   main: The branch in your local repository being pushed to the corresponding branch in the remote repository.

   git pull: Fetches updates from the remote repository and merges them into your current local branch.
   origin: The name of the remote repository from which updates are fetched.
   main: The branch you want to pull changes from.
   ```

#### **Task 11: Cloning a Repository**
1. Clone a remote repository:  
   ```bash
   git clone https://github.com/your-username/repo.git
   ```
   ```
   Explaination :-  git clone: This command copies the repository from the Remote server to Local Machine.

---

### **Part 5: Advanced Git**

#### **Task 12: Stashing Changes**
1. Save uncommitted changes:  
   ```bash
   git stash
   ```
2. Apply stashed changes:  
   ```bash
   git stash apply
   ```
3. Drop the stash:  
   ```bash
   git stash drop
   ```
   ```
   Explaination :- git stash: The git stash command is used to temporarily save changes you've made to your working directory without committing them.After stashing, your working directory is reset to match the last commit.
   
   git stash apply: Applies the most recent stash (stash@{0}) back to the working directory without removing it from the stash list.

   git stash drop: Removes the most recent stash (stash@{0}) from the stash list.
   ```

#### **Task 13: Tagging Commits**
1. Create and annotate a tag:  
   ```bash
   git tag -a v1.0 -m "Version 1.0 release"
   ```
2. Push the tag to the remote:  
   ```bash
   git push origin v1.0
   ```
   ```
   Explaination :- git tag: This command creates a tag on the current commit.
   -a v1.0: The -a flag specifies that you`re creating an annotated tag .The v1.0 is the name of the tag.

   -m "Version 1.0 release": This provides a message for the tag.

   git push origin v1.0: This command pushes the tag (v1.0) to the remote repository.

#### **Task 14: Rewriting Commit History**
1. Use interactive rebase to modify commit messages:  
   ```bash
   git rebase -i HEAD~3
   ```
   - Replace `pick` with `edit` or `squash` as needed.
   ```
   Explaination :- git rebase -i: The -i flag stand for Interactive rebaseb,which allows you to manipulate commits.
   HEAD~3: HEAD~3 means 3 commits before the current commit.
   ```

#### **Task 15: Cherry-Picking Commits**
1. Apply a specific commit to another branch:  
   ```bash
   git cherry-pick <commit-hash>
   ```
   ```
   Explaination :- git cherry-pick <commit-hash>: This command takes the changes introduced by the commit with the specified <commit-hash> and applies those changes to your current working branch as a new commit. 
   ```
---

### **Part 6: Collaboration**

#### **Task 16: Forking and Pull Requests**
1. Fork a repository and clone it locally:  
   ```bash
   git clone https://github.com/your-username/forked-repo.git
   ```
2. Make changes and push them:  
   ```bash
   git checkout -b fix-typo
   echo "Typo fixed" >> README.md
   git commit -m "Fixed a typo"
   git push origin fix-typo
   ```
3. Open a pull request on GitHub.
   ```
   Explaination :- Fork: Forking a repository on GitHub creates a copy of someone else's repository under your own GitHub account.

   git clone <forked-repo-url>: This command clones your forked repository from GitHub to your local machine. 

   git checkout -b <branch-name> : This command creates a new branch and switches to it.

   echo "Typo Fixed" >> README.md: This command adds the text "Typo fixed" to the end of the README.md file.

   git add README.md: Stages the README.md file for committ.

   git commit -m "Fixed a typo": Commits the staged changes, with a message.

   git push origin fix-typo: This command pushes fix-typo branch and its changes the fork on GitHub.
   ```

   #### **Task 17: Simulating Team Collaboration**
   1. Simulate a conflict by having two users modify the same file.

   2. Practice resolving the conflict as a team.
   
   Explaination :- 1. Create two branches:
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
   
---

### **Part 7: Ignoring Files**

#### **Task 18: Using .gitignore**
1. Create a `.gitignore` file:  
   ```bash
   echo "node_modules/" > .gitignore
   git add .gitignore
   git commit -m "Added .gitignore"
   ```
2. Verify that ignored files are not staged:  
   ```bash
   git status
   ```
   ```
   Explanation :-  echo "node_modules/" > .gitignore: This command creates a .gitignore file and adds the line node_modules/ to it.

   git add .: The command stages all changes in the current directory for commit.

   git commit -m "":

   git status: This command shows the current state of your working directory and staging area.
   ``` 
---

### **Part 8: Automation and Cleanup**

#### **Task 19: Cleaning the Repository**
1. Remove untracked files:  
   ```bash
   git clean -f
   ```
   ```
   Explanation :- git clean -f: This command is used to remove untracked files from your working directory.
   ```

#### **Task 20: Aliases and Shortcuts**
1. Create an alias for frequently used commands:  
   ```bash
   git config --global alias.st status
   git config --global alias.cm commit
   ```
2. Use the alias:  
   ```bash
   git st
   git cm -m "Message"
   ```
   ```
   Explanation :- git config: Modifies Git's configuration files.
   --global: Applies the configuration globally for all repositories on your system.

   alias.st: Creates a shortcut for the git status command. After this, you can type git st instead of git status.

   alias.cm: Creates a shortcut for the git commit command. After this, you can type git cm instead of git commit.
   
   git st: Execute the git status.

   git cm -m "M": Execute the git commit im "message".
   ```
---