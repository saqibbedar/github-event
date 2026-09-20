# Git CheatSheet

1. **Check status**: 

    ```bash
    git status 
    git status --short 
    git status --short --branch
    ```

2. **Log**

    ```bash
    git log
    git log --oneline
    git log --oneline --decorate
    git log --oneline --decorate --graph
    git log --oneline --decorate --graph --all
    git log --oneline --decorate --graph --all --color

    # remove messy noise by --simplify-by-decoration (clean output)
    git log --oneline --decorate --graph --all --simplify-by-decoration
    
    # if repo has huge history then specify limit i.e., 20
    git log --oneline --decorate --graph --all -20

    # Make an alias
    git config --global alias.adog "log --oneline --decorate --graph --all"
    ```

3. **diff**:

    ```bash
    # 1. Base command: Shows all unstaged changes in the working directory
    git diff

    # 2. Add color: Forces colored output (usually on by default, helps highlight +/- lines)
    git diff --color

    # 3. Focus on staged: Shows changes you have already run `git add` on (crucial before committing)
    git diff --staged        # --cached works as an exact synonym

    # 4. Word-by-word comparison: Highlights changes inside lines instead of replacing the whole line
    git diff --word-diff

    # 5. File summaries only: Shows which files changed and how much (lines added/deleted) without code details
    git diff --stat

    # 6. Name and status only: The cleanest view; just gives a list of filenames and if they were Modified (M), Added (A), or Deleted (D)
    git diff --name-status

    # 7. Filter by specific files: Restrict the output to a specific file or folder to remove background noise
    git diff -- path/to/file.txt

    # 8. Compare across points: See differences between two branches, commits, or a branch vs your working directory
    git diff main feature-branch

    # Make an alias (Example: 'git dc' to quickly check your staged changes before committing)
    git config --global alias.dc "diff --staged"

    # Make an alias (Example: 'git dstat' for a clean high-level view of unstaged changes)
    git config --global alias.dstat "diff --stat"
    ```

4. **Branches**:

    ```bash
    # create & switch to created branch
    git switch -c b-name

    # delete branch locally
    git branch -D b-name

    # list branches
    git branch --list
    ```

5. **Config & Aliases**:

    ```bash
    # 1. Make alias

    # create alias for git log and its several flags
    git config --global alias.adog "log --oneline --decorate --graph --all"

    # run via alias
    git adog


    # 2. View your git configs

    # view every config
    git config --list

    # view global configs only
    git config --global --list

    # check specific alias
    git config alias.adog       # output: alias.adog=log --oneline --decorate --graph --all


    # 3. Edit configs

    # 3.1. Method 1 (CLI): You can list the config and then update any config, for example
    git config --global alias.adog "log --oneline --decorate --graph --all --color"

    # 3.2. Method 2 (Open the Config File in an Editor): This approach is best for managing multiple aliases.
    git config --global --edit


    # 4. Delete Config
    git config --global --unset alias.adog
    ```
    
