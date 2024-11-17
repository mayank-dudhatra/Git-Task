### **Task List: Focused on Advanced Git Operations**

### **Part 1: Understanding and Using `git stash`**

#### **Task 1: Save Changes Temporarily with `git stash`**
1. Make changes to a file without committing:  
   ```bash
   echo "Temporary changes" >> temp-file.txt
   ```
2. View the status of changes:  
   ```bash
   git status
   ```
   - **Output**:  
     ```
     Changes not staged for commit:
       modified:   temp-file.txt
     ```

3. Stash the changes:  
   ```bash
   git stash
   ```
   - **Explanation**: This command saves changes to a stash and restores the working directory to the last commit state.

4. View the stashed changes:  
   ```bash
   git stash list
   ```
   - **Output**:  
     ```
     stash@{0}: WIP on main: 27e5f23 Added temporary changes
     ```
     ```
     Explanation :- echo "Text" >> temp-file.txt: This command create new file name temp-file.txt and write Text inside it.

     >>: Unlike >, this appends the text to the file without overwriting its existing content.

     git status: git status: This command displays the state of the working directory and the staging area.

     git stash: This command temporarily saves your uncommitted changes so that your working directory becomes clean and reverts to the state of the last commit.

     git stash list: This command lists all stashed changes saved in Git's stash stack.
     ```

#### **Task 2: Apply and Drop Stashed Changes**
1. Apply the most recent stash:  
   ```bash
   git stash apply
   ```
2. Drop the most recent stash after applying it:  
   ```bash
   git stash drop
   ```

3. Alternatively, to apply a specific stash:  
   ```bash
   git stash apply stash@{1}
   ```
   ```
   Explanation :- git stash apply: Applies the changes from the most recent stash (stash@{0}) to your working directory.

   git stash drop: Deletes a specific stash from the stash stack.
   ```

#### **Task 3: Stash Untracked Files**
1. Stash changes, including untracked files:  
   ```bash
   git stash -u
   ```
2. Apply stashed changes including untracked files:  
   ```bash
   git stash apply
   ```
   ```
   Explanation :- git stash -u: git stash only stashes tracked files but But by adding -u untracked file are also stashed.

   git apply: Restores all changes from the most recent stash, including tracked and untracked files if they were included when the stash was created with -u.
   ```
---

### **Part 2: Rewriting History with `git rebase`**

#### **Task 4: Rebase Commits to a New Base**
1. Rebase the current branch onto `main`:  
   ```bash
   git rebase main
   ```
   - **Explanation**: This command applies the commits from your current branch on top of the latest commit from `main`.

2. Resolve any conflicts that may arise during rebase, and continue:  
   ```bash
   git rebase --continue
   ```
   ```
   Explanation :- 
   ```

#### **Task 5: Canceling a Rebase**
1. If a rebase goes wrong, abort it:  
   ```bash
   git rebase --abort
   ```
   ```
   Explanation :- 
   ```

---

### **Part 3: Interactive Rebase (`git rebase -i`)**

#### **Task 6: Use Interactive Rebase to Modify Commit History**
1. View the last few commits:  
   ```bash
   git log --oneline
   ```

2. Start an interactive rebase for the last 3 commits:  
   ```bash
   git rebase -i HEAD~3
   ```
   - **Explanation**: This opens an editor with the list of commits in the last 3 commits.

3. Modify the commits by changing `pick` to one of the following:
   - `squash` (combine commits)
   - `reword` (edit commit message)
   - `edit` (edit commit content)
   - `drop` (remove commit)

4. Example of squashing two commits:
   - Change the second commit from `pick` to `squash` and save.
   - Git will combine the commit messages for the squashed commit.

   ```
   Explanation :- git log --oneline :- This command display the commit history into single line per commit for quick review.

    git rebase -i: The -i flag stand for Interactive rebaseb,which allows you to manipulate commits.
    HEAD~3: HEAD~3 means 3 commits before the current commit.

    pick: Use the commit as itis without any modifications.
    squash: Combines this commit with the one above it into a single commit.
    reword: Edit the commit message while keeping the commit content unchanged.
    edit: Pause the rebase and allow you to modify the content of the commit.
    drop: Remove the commit entirely from history.
   ```

#### **Task 7: Complete Interactive Rebase**
1. After modifying the commits, save and close the editor.
2. Resolve any conflicts if prompted, then continue the rebase:  
   ```bash
   git rebase --continue
   ```

---

### **Part 4: Cherry-Picking Commits (`git cherry-pick`)**

#### **Task 8: Pick a Specific Commit**
1. View the commit history to find the commit hash you want to cherry-pick:  
   ```bash
   git log --oneline
   ```

2. Cherry-pick a specific commit by its hash:  
   ```bash
   git cherry-pick <commit-hash>
   ```
   - **Example**:  
     ```bash
     git cherry-pick e23d8a7
     ```

3. Resolve conflicts if any, then commit the changes:  
   ```bash
   git add .
   git cherry-pick --continue
   ```
   ```
   Explanation :- git log --oneline :- This command display the commit history into single line per commit for quick review.

   git cherry-pick <commit-hash>: This command takes the changes introduced by the commit with the specified <commit-hash> and applies those changes to your current working branch as a new commit. 

   git add . : The command stages all changes in the current directory for commit.

   git cherry-pick --continue: command to resolve the conflicts and continue with the cherry-picking process.    
   ```
---

### **Part 5: Tagging Commits (`git tag`)**

#### **Task 9: Tag a Commit**
1. Tag the current commit with a version number:  
   ```bash
   git tag -a v1.0 -m "Initial release"
   ```

2. List all tags:  
   ```bash
   git tag
   ```
   ```
   Explanation :-  git tag: This command creates a tag on the current commit.
   -a v1.0: The -a flag specifies that we are creating an annotated tag .The v1.0 is the name of the tag.

   -m "Initial Release": This provides a message for the tag.
   
   git tag: This command display a list of all tags in the repository
   ```

#### **Task 10: Tag a Specific Commit**
1. Tag a specific commit by its hash:  
   ```bash
   git tag -a v1.1 <commit-hash> -m "Bug fix"
   ```
   ```
   Explanation :-   git tag: This command creates a tag on the current commit.
   -a v1.0: The -a flag specifies that we are creating an annotated tag .The v1.0 is the name of the tag.
   
   <commit-hash>:   git tag: This command creates a tag on the current commit.
   -a v1.0: The -a flag specifies that we are creating an annotated tag .The v1.0 is the name of the tag.

   -m "Bug fix": This provides a message for the tag.
   
   ```
#### **Task 11: Push Tags to Remote**
1. Push a specific tag to the remote repository:  
   ```bash
   git push origin v1.0
   ```

2. Push all tags to the remote repository:  
   ```bash
   git push --tags
   ```
   ```
   git push origin v1.0: This command pushes the tag (v1.0) to the remote repository.

   git push --tags: This is used to push all tags in your local repository to the remote repository.

   git push origin v1.0: This command pushes the tag (v1.0) to the remote repository.
   ```
---

### **Part 6: Working with Remote Repositories**

#### **Task 12: Add a Remote Repository**
1. Add a remote repository URL to the project:  
   ```bash
   git remote add origin https://github.com/username/repo.git
   ```
   ```
   Explanation :- git remote add origin: This command adds a remote repository to your local Git repository. The remote repository is where your code can be pushed or pulled from.
   ```

#### **Task 13: Fetch Changes from Remote**
1. Fetch changes from the remote repository without merging them:  
   ```bash
   git fetch origin
   ```

2. View fetched branches:  
   ```bash
   git branch -r
   ```
   ```
   Explanation :- git remote origin :- Fetches the latest changes from the remote repository (here, origin) into your local repository.

   git branch -r: this command is is used to list all remote branches that your Git repository knows about.
   ```

#### **Task 14: Pull Changes from Remote**
1. Pull the latest changes from the remote repository and merge them into the local branch:  
   ```bash
   git pull origin main
   ```
   ```
   Explanation :- git pull origin main: This command is used to fetch changes from the main branch of the remote repository origin and merge them into your current local branch.
   ```

#### **Task 15: Push Changes to Remote**
1. Push local changes to the remote repository:  
   ```bash
   git push origin main
   ```

2. Push a new branch to the remote repository:  
   ```bash
   git push origin feature-branch
   ```
   ```
   Explanation :-  git push origin main: This Command is used to push the changes from local to main branch on the remote repository named origin.

   git push origin feature-branch :-  git push origin feature-branch: This Command is used to push the changes from local to feature-branch on the remote repository named origin.
   ```

#### **Task 16: Delete Remote Branch**
1. Delete a remote branch:  
   ```bash
   git push origin --delete feature-branch
   ```
   ```
   Explanation :- git push origin --delete feature-branch :- is used to delete a branch named feature-branch from the remote repository (origin).
   ```
---

### **Part 7: Forking and Contributing to Open-Source Projects**

#### **Task 17: Fork a Repository on GitHub**
1. Go to a repository on GitHub and click **Fork** in the top right corner to create your own copy of the repository.

2. Clone the forked repository to your local machine:  
   ```bash
   git clone https://github.com/your-username/repo.git
   ```
   ```
   Explanation :-  Fork: Forking a repository on GitHub creates a copy of someone else's repository under your own GitHub account.

   git clone <forked-repo-url>: This command clones your forked repository from GitHub to your local machine.
   ``` 

#### **Task 18: Make Changes and Commit**
1. Create a new branch for your changes:  
   ```bash
   git checkout -b fix-typo
   ```

2. Make changes to the code (e.g., fix a typo in `README.md`), stage, and commit them:  
   ```bash
   git add README.md
   git commit -m "Fixed typo in README.md"
   ```
   ```
   Explanation :- git checkout -b <branch-name> : This command creates a new branch and switches to it.

   git add README.md: Stages the README.md file for committ.

   git commit -m "Fixed typo in README.md": Commits the staged changes, with a message.
   ```

#### **Task 19: Push Changes to Your Fork**
1. Push the changes to your remote fork:  
   ```bash
   git push origin fix-typo
   ```
   ```
   Explanation :- git push origin fix-typo: This command push changes from local to fix-typo branch on the remote repository named origin and its changes the fork on GitHub.
   ```

#### **Task 20: Create a Pull Request**
1. Go to your forked repository on GitHub, click on **Compare & Pull Request**.
2. Write a description of your changes and submit the pull request to the original repository.
   ```
   Explanation :- 
   1. Go to Your Forked Repository.

   2. Click on Compare & Pull Request.

   3. Write a Description of Your Changes.

   4. Submit the Pull Request.
   ```

#### **Task 21: Sync Your Fork with the Original Repository**
1. Add the original repository as a remote source:  
   ```bash
   git remote add upstream https://github.com/original-owner/repo.git
   ```

2. Fetch changes from the original repository:  
   ```bash
   git fetch upstream
   ```

3. Merge changes from the original repository into your local branch:  
   ```bash
   git checkout main
   git merge upstream/main
   ```

4. Push the changes to your fork:  
   ```bash
   git push origin main
   ```
   ```
   Explanation :- git remote add upstream: This command adds the original repository as a remote called upstream.

   git fetch upstream: Retrieves the latest changes (commits, branches, tags) from the upstream repository.

   git checkout main: this command switch from any branch to main branch.

   git merge upstrem/main: Combines the changes from the original repository into your local main branch.

   git push origin main: This command pushes the updated main branches 
   ```

---

### **Consolidated Summary**

1. **Stashing**: Saving and applying uncommitted changes temporarily.
2. **Rewriting History**: Using `git rebase` and `interactive rebase` to modify and clean up commit history.
3. **Cherry-Picking**: Selecting specific commits from another branch.
4. **Tagging**: Labeling commits for versioning.
5. **Working with Remote Repositories**: Managing remotes, pushing, pulling, and fetching changes.
6. **Forking & Contributing**: Forking repositories, contributing to open-source projects, and syncing your fork.
