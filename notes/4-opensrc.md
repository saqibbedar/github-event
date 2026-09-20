# Open Source Workflow (Make your first contribution)

1. **Step 1**: Fork a repo.

2. **Step 2**: Clone your forked repository 

    ```bash
    git clone https://github.com/<your-username>/<repository>.git
    ```

3. **Step 3**: Link to the Original Project (Upstream)
    
    ```bash
    # Tell your local Git where the original owner's repository is
    git remote add upstream https://github.com/<owner>/<repository>.git
    git remote -v
    ```
4. **Step 4**: Sync changes

    ```bash
    git pull upstream main # just like git pull origin main for your own repo changes

    # OR other way to do it

    # Fetch the latest changes from the original owner's repo
    git fetch upstream

    # Switch to your local main branch
    git switch main

    # Merge the owner's latest changes into your local main
    git merge upstream/main
    ```

5. **Step 6**: Create your feature-branch
    
    ```bash
    git switch -c feature-branch
    ```

6. **Step 7**: Make Changes & Commit

    ```bash
    # Stage your modified files
    git add .

    # Commit your changes locally
    git commit -m "Your descriptive commit message"
    ```

7. **Step 8**: Push changes to your fork

    ```bash
    git push origin feature-branch
    ```

    > Note: After running the push command, GitHub will output a direct web link in your terminal. You can click that link to instantly open the Pull Request page on GitHub.

<br>

8. **Step 8**: Create the Pull Request (PR)

   - Open your browser and navigate to your fork on GitHub.
   - You will see a yellow banner at the top showing your newly pushed branch. Click Compare & pull request.
   - Ensure the base repository points to the original project and the head repository points to your fork.
   - Write a descriptive title and fill out the PR template outlining what you changed and why.
   - Click Create pull request.


<br>

## 💡 Golden Rules for Your First Pull Request

* Read the CONTRIBUTING.md file: Most repositories have a guide detailing their specific rules. Always check this file before doing anything.
* Keep it tiny: Your first commit should ideally be a single-line or single-sentence fix.
* Be patient: Maintainers are busy volunteers. It might take a few days (or even weeks) for them to review and merge your work.