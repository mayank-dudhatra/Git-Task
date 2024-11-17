### **Task List: Focused on Repository Management, Commits, Branching, and Merging**

### **Part 1: Creating and Cloning Repositories**

#### **Task 1: Create a Local Git Repository**
1. Create a new project folder:  
   ```bash
   mkdir MyProject
   cd MyProject
   ```
2. Initialize it as a Git repository:  
   ```bash
   git init
   ```
   - **Explanation**: This creates a `.git` folder that stores the repository's metadata and history.

3. Verify the repository status:  
   ```bash
   git status
   ```
   - **Example Output**:  
     ```
     On branch main
     No commits yet
     nothing to commit (create/copy files and use "git add" to track)
     ```
     ```
     Expalnation :- mkdir: This is the Command is used to Create New Folder.

     cd: This is the Command is used to move into any Folder.

     git init: This Initialize the current folder as Repository. After Initialize, a hidden .git folder apper in the directory. 

     git status: This command shows the current state of your working directory and staging area.
     ```

#### **Task 2: Clone a Remote Repository**
1. Clone a GitHub repository:  
   ```bash
   git clone https://github.com/username/repo.git
   ```
   - **Explanation**: This command downloads the repository to your local system.  

2. Verify the cloned repository structure:  
   ```bash
   cd repo
   ls -a
   ```
   - **Output**: The `.git` folder should be present.
   ```
   Explanation :- git clone: This command copies the repository from the Remote server to Local Machine.

   cd repo: Navigate to the cloned repository.

   ls -a: View all files, including hidden ones like .git.
   ```
---

### **Part 2: Understanding Commits and Commit Messages**

#### **Task 3: Commit Changes Locally**
1. Create a new file and add content:  
   ```bash
   echo "Welcome to Git" > README.md
   ```
2. Stage the file:  
   ```bash
   git add README.md
   ```
   - **Explanation**: `git add` moves changes to the staging area.

3. Commit the staged file:  
   ```bash
   git commit -m "Initial commit: Added README.md"
   ```
   - **Explanation**: Commits save the current state of the repository with a message describing the change.

   ```
   Explanation :-  echo "Hello Git" > file1.txt : This command creates a new file named file1.txt and writes the text "Hello Git" into it. 

   git add . : This Command Stage all chnages in the directory and Track all the files.

   git commit: This Command save a screenshot of the current state of your Repository.
   -m : Allow you to add commit message.
   ```


#### **Task 4: Write Effective Commit Messages**
1. Create a detailed commit message:  
   ```bash
   git commit -m "Added initial version of README.md with project overview"
   ```
   - **Explanation**: Commit messages should follow conventions such as starting with a capital letter, being concise, and using the imperative mood.

2. Commit multiple files with one message:  
   ```bash
   touch file1.txt file2.txt
   git add .
   git commit -m "Added two new files for feature setup"
   ```
   ```
   Explanation :- git commit: Saves changes from the staging area to the repository's history.
   -m: Allows you to include a commit message directly in the command line.

   touch <file-name>: Creates multiple empty files.

   git add . : This Command Stage all chnages in the directory and Track all the files.

   git commit -m "message": Saves all staged changes to the repository's history with a single commit message.
   ```
---

### **Part 3: Viewing Commit History with `git log`**

#### **Task 5: View Detailed Commit History**
1. View full commit logs:  
   ```bash
   git log
   ```
   - **Explanation**: Shows a detailed list of commits with hash, author, date, and message.

2. View commit history in a compact format:  
   ```bash
   git log --oneline
   ```
   - **Example Output**:  
     ```
     e23d8a7 Added initial version of README.md
     f7b3c62 Initial commit: Added README.md
     ```
     ```
     Explanation :- git log: This command displays a detailed list of all commits in the current branch. 

     git log --oneline: The --oneline flag condenses the commit history into a single line per commit for quick review.

#### **Task 6: Customize Log Outputs**
1. View logs with a graphical representation:  
   ```bash
   git log --oneline --graph --decorate
   ```
2. Filter logs for a specific file:  
   ```bash
   git log README.md
   ```
   ```
   Explanation :- git log:  This command displays a detailed list of all commits in the current branch. 
   --oneline: Shows each commit as a single line, including a shortened commit hash and message.
   --graph: Adds a graphical representation of the commit history, including branch and merge relationships.
   --decorate: Shows references such as branch names, tags, or HEAD pointers. 

   git log Readme.md: Filters the commit history to show only those commits that affected the specified file
   ```
---

### **Part 4: Understanding Branching and Merging**

#### **Task 7: Understanding Branching**
1. List all branches:  
   ```bash
   git branch
   ```
   - **Explanation**: Displays the current branch and all other branches.

2. Create a new branch:  
   ```bash
   git branch feature-branch
   ```
   - **Explanation**: Creates a new branch without switching to it.

3. Switch to the new branch:  
   ```bash
   git checkout feature-branch
   ```
   - **Alternative Command**:  
     ```bash
     git checkout -b feature-branch
     ```
     - **Explanation**: Creates and switches to the branch in one command.
     ```
     Explanation :- git branch: This command lists all the branches in your Git repository.

     git branch <branch-name>: This command create a new branch.

     git checkout: This command is used to switch into any branch.

     git checkout -b <name>: This Command create new branch and switch into it in one step.
     ```
---

### **Part 5: Creating and Working with Branches**

#### **Task 8: Make Changes in a Branch**
1. Add content to a file in the new branch:  
   ```bash
   echo "Feature in progress" > feature.txt
   git add feature.txt
   git commit -m "Added feature.txt in feature-branch"
   ```
   ```
   Explanation :- echo "Feature in Progress" > file1.txt : This command creates a new file named feature.txt and writes the text "Hello Git" into it. 

   git add . : This Command Stage all chnages in the directory and Track all the files.

   git commit: This Command save a screenshot of the current state of your Repository.
   -m : Allow you to add commit message .
   ```

#### **Task 9: Merging Branches**
1. Switch back to the `main` branch:  
   ```bash
   git checkout main
   ```
2. Merge the `feature-branch` into `main`:  
   ```bash
   git merge feature-branch
   ```
   - **Explanation**: Combines the changes from `feature-branch` into `main`.
   ```
   Explanation :- git checkout main: This command switch any branch to main branch.

   git merge: This command is used to combine the work of one branch into another.
   ```
---

### **Part 6: Resolving Merge Conflicts**

#### **Task 10: Simulate a Merge Conflict**
1. Modify the same line in a file on two branches:  
   ```bash
   echo "Main branch content" > conflict.txt
   git add conflict.txt
   git commit -m "Added conflict.txt in main branch"
   ```
   ```
   Explanation :- echo "ain branch content" > conflict.txt : This command creates a new file named conflict.txt and writes the text "Hello Git" into it. 

   git add . : This Command Stage all chnages in the directory and Track all the files.

   git commit: This Command save the staged change of the current state of your Repository.
   -m : Allow you to add commit message .
   ```

2. Switch to the other branch and make conflicting changes:  
   ```bash
   git checkout feature-branch
   echo "Feature branch content" > conflict.txt
   git add conflict.txt
   git commit -m "Modified conflict.txt in feature-branch"
   ```
   ```
   Explanation :- git checkout feature-branch: This command switch any branch to feature-branch.

    echo "Feature branch content" > conflict.txt : This command creates a new file named conflict.txt and writes the text "Hello Git" into it.This file created in feature-branch. 

   git add . : This Command Stage all chnages in the directory and Track all the files.

   git commit: This Command save the staged change of the current state of your Repository.
   -m : Allow you to add commit message .
   ```

3. Merge `feature-branch` into `main`:  
   ```bash
   git checkout main
   git merge feature-branch
   ```
   ```
   Explanation :- git checkout main :- This command switch the branch to main branch.

   git merge: This command is used to combine the work of one branch into another.
   ```   

4. Resolve the conflict by editing the file and choosing the correct version:  
   - Open `conflict.txt` and decide which changes to keep.
   - Stage the resolved file:  
     ```bash
     git add conflict.txt
     ```
   - Commit the merge:  
     ```bash
     git commit -m "Resolved conflict in conflict.txt"
     ```
     ```
     Explanation :- 

---

### **Part 7: Deleting and Renaming Branches**

#### **Task 11: Delete a Branch**
1. Delete a local branch:  
   ```bash
   git branch -d feature-branch
   ```
   - **Explanation**: This deletes the branch only if it has been fully merged.  

2. Force-delete a branch:  
   ```bash
   git branch -D feature-branch
   ```
   - **Explanation**: Deletes the branch even if it hasn’t been merged.

#### **Task 12: Rename a Branch**
1. Rename the current branch:  
   ```bash
   git branch -m new-branch-name
   ```
2. Rename another branch (not checked out):  
   ```bash
   git branch -m old-branch-name new-branch-name
   ```

---

### **Consolidated Flow Summary**

1. Start by creating and cloning repositories.
2. Learn to commit changes effectively with clear messages.
3. Explore commit history using various `git log` commands.
4. Understand branching and practice creating, switching, and merging branches.
5. Dive into resolving merge conflicts.
6. End by managing branches through deletion and renaming.
