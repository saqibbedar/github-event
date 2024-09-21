# GitHub learn what matters 🚀

### 1. Define git as VCS?

Git is called a version control system (VCS) because it helps manage changes to files and directories over time. Git is primarily about tracking changes and collaboration.

### 2. You have a repository already created on GitHub, and you’ve also initialized a new repository locally. Your goal is to connect the local repository to the existing GitHub repository. How do you add the GitHub repository as the remote (i.e., set it as the origin) so that you can push your local changes to it?

- git init
- git add .
- git commit -m "Initial commit"
- git branch -M main // -M flag forcefully rename the branch name as it stands for move
- git pull origin main --allow-unrelated-histories // --allow-unrelated-histories flag is necessary because you have separate histories (one local and one remote) that need to be merged.
- git remote add origin "URL"
- git push -u origin main

### 3. How uninitialize a git repository?

To uninitialize a git repository, you need to go to the repository folder where .git file was created and after which remove the .git file using following command

- rmdir /s /q .git (windows cmd)
- Remove-Item -Recurse -Force .git (windows powershell)

### 4. How do I un-stage changes ?

To un-stage all changes run following command:

- git reset (un-stage all changes)
- git reset "filename" (any specific change)

### 5. What does mean by stage?

 In Git, the process of saving changes is split into multiple steps, and staging is one of the key steps. When you "stage changes" using git add, it means that you are preparing specific changes (modified, added, or deleted files) to be included in the next commit.


### 6. How do I undo a commit?

- git reset --soft HEAD~1: Undo the last commit but keep changes staged.

- git reset --mixed HEAD~1: Undo the last commit and unstage changes (default behavior).

- git reset --hard HEAD~1: Undo the last commit and discard all changes.

- git revert "commit-hash": Create a new commit that reverses the changes of a specific commit.

### 7. You are working on a collaborative project with multiple branches. You need to add a new feature on a specific branch named feature-xyz. Describe the steps you would take to switch to this branch, make changes, commit those changes, and then push the updates to the remote repository. Additionally, explain how you would merge these changes into the main branch afterward.

- Clone the Repository:

    ```bash
    git clone https://github.com/username/repo.git
    cd repo
    ```
- List All Branches 

    ```bash
    git branch -a
    ```

- Switch to the Desired Branch

    ```bash
    git checkout branch-name
    ```

- Switch to the Desired Branch

    ```bash
    git checkout branch-name
    ```

- Update the Feature

    Make your changes to the code as needed. Once you’re done, check the status of your changes:

    ```bash
    git status
    ```

- Stage and Commit Your Changes

    ```bash
    git add .
    git commit -m "Describe your changes"
    ```
- Push Your Changes to the Remote Branch

    ```bash
    git push origin branch-name
    ```

- Merge Changes (if needed)

    1. Switch to the Target Branch (e.g., main):

        ```bash
        git checkout main
        ```
    2. Fetch the Latest Changes (optional but recommended):
        ```bash
        git fetch origin
        ```
    3. Merge the Feature Branch into the Target Branch:
        ```bash
        git merge branch-name
        ```
- Push the Merged Changes to the Remote Repository

    ```bash
    git push origin main
    ```
