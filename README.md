# Assignment 3: Branching Strategies & Merge Conflicts

## 🎯 Objective

This project demonstrates hands-on experience with Git branching strategies, specifically implementing the GitHub Flow. The primary goal was to simulate a feature development process, intentionally create merge conflicts, and successfully resolve them, thereby solidifying understanding of version control in a collaborative environment.

---

## 🔗 Link to GitHub Repository

You are currently viewing the repository that fulfills this assignment's requirements:

* **Repository URL:** https://github.com/Sivanithink/Merge_Conflict-Assign-3
---

## 📸 Screenshots: Merge Conflict & Resolution Process

The following screenshots document the key stages of encountering and resolving a merge conflict:

1.  **Pull Request for `feature/update-styling` (Ready to Merge):**
    *Description: This screenshot shows the pull request for the `feature/update-styling` branch (PR #1) indicating it is able to be merged into `master`.*
    <img width="619" alt="ass 3 1 pull request 1" src="https://github.com/user-attachments/assets/a08659b4-2915-41f6-9474-bf0c1c42d8ba" />

    ```
    ```

2.  **Merge Conflict Notification on GitHub for `feature/add-content` (PR #2):**
    *Description: This screenshot shows the pull request for the `feature/add-content` branch (PR #2) clearly indicating "This branch has conflicts that must be resolved" after `feature/update-styling` was presumably merged.*
    <img width="751" alt="ass 3 3 pull req 2" src="https://github.com/user-attachments/assets/a2f90ec9-af52-4589-86fc-f0a5d8db5c6c" />

    ```
    ```

3.  **Conflict Markers in `index.html` (GitHub Conflict View):**
    *Description: This screenshot displays the `index.html` file within GitHub's conflict resolution interface, clearly showing the `<<<<<<< feature/add-content`, `=======`, and `>>>>>>> master` conflict markers.*
   <img width="611" alt="ass 3 conflict 1" src="https://github.com/user-attachments/assets/77ccd9d6-59e1-4f6a-abfe-7e8add7a28a7" />
   <img width="461" alt="ass conflict error" src="https://github.com/user-attachments/assets/81900946-740e-4d17-ad56-72e6b9f77502" />

    ```
    ```

5.  **Successfully Resolved and Merged `feature/add-content` Pull Request (PR #2):**
    <img width="498" alt="ass 3conflit resolve 2" src="https://github.com/user-attachments/assets/8f9ecbb3-3e1b-4891-85e4-b8b6a2dd31c0" />

    ```
    ```

---

## 🛠️ How I Fixed the Merge Conflict

Working on this assignment, I ran into a merge conflict, and here’s how I sorted it out:

1.  **Figuring Out the Problem:**
    * The main issue popped up in the `index.html` file.
    * It happened when I tried to merge my `feature/add-content` branch into the `master` branch. The tricky part was that `master` already had some new changes from another branch I'd merged earlier (`feature/update-styling`), and both of these branches had changed the same part of `index.html`.
    * Specifically, both branches wanted to change the main heading (the `<h1>` tag). When I looked at the conflict markers Git put in the file, I could see:
        * My `feature/add-content` branch was trying to make the heading: `<h1>Welcome to My Enhanced Page</h1>`
        * But, the `master` branch (because of the `feature/update-styling` changes) already had: `<h1>Welcome to My Updated Page</h1>`

2.  **Sorting it Out Locally:**
    * First things first, I switched to my local `master` branch and did a `git pull origin master`. This made sure I had the very latest version of `master` on my computer, including the changes from that first feature branch.
    * Then, I switched back to my `feature/add-content` branch.
    * To actually see and deal with the conflict on my machine, I ran `git merge master`. This tried to bring those `master` branch changes into my `feature/add-content` branch and, as expected, it flagged the conflict in `index.html`.
    * I opened `index.html` in my code editor. I could clearly see the lines Git uses to show a conflict – those `<<<<<<<`, `=======`, and `>>>>>>>` markers around the different `<h1>` versions.
    * **My Decision:** *(CHOOSE THE OPTION THAT BEST DESCRIBES WHAT YOU DID AND REPHRASE IT IN YOUR OWN WORDS. DELETE THE OTHER OPTIONS.)*
        * **Option A (Kept 'Enhanced Page'):** I looked at both versions and decided that the heading from my `feature/add-content` branch (`<h1>Welcome to My Enhanced Page</h1>`) was the one I wanted to keep. So, I deleted the version from `master` and the conflict markers.
        * **Option B (Kept 'Updated Page'):** After comparing them, I figured the heading already in `master` (`<h1>Welcome to My Updated Page</h1>`) made more sense, so I decided to go with that one. I removed the lines from `feature/add-content` and the conflict markers.
        * **Option C (Combined):** I thought a bit of both would be best, so I actually edited the line to create a new heading that combined the ideas, like `<h1>Welcome to My Enhanced and Updated Page</h1>` (or whatever your specific combination was). Then I removed all the conflict marker lines.
    * Once I had the `<h1>` tag looking exactly how I wanted it, I made sure to delete all those `<<<<<<<`, `=======`, and `>>>>>>>` lines that Git added.

3.  **Saving and Sharing My Fix:**
    * With `index.html` all cleaned up, I staged the file using `git add index.html`.
    * Then, I committed my fix with a message that explained what I did, something like `git commit -m "Fixed merge conflict in page title"`.
    * Finally, I pushed my `feature/add-content` branch, now with the conflict resolved, back up to GitHub using `git push origin feature/add-content`.

4.  **Finishing the Merge on GitHub:**
    * Once my fixed `feature/add-content` branch was on GitHub, the Pull Request page automatically updated. The warning about conflicts was gone, and it showed that my branch was now clear to merge.
    * So, I went ahead and clicked the button on GitHub to merge my `feature/add-content` branch into `master`, successfully getting all my changes in.

---

# Assignment 4: Git Hooks & Automation

### Git Hooks & Husky
I learned that Git provides "hooks," which are essentially scripts that Git can automatically execute at specific points in its lifecycle (e.g., before a commit or before a push). However, managing these hooks across a team can be challenging because they reside in the local `.git/hooks` directory, which isn't version-controlled.
**`Husky`** is the tool I used to solve this. It simplifies the management of Git hooks by allowing them to be defined in project configuration files (within the `.husky/` directory) that are shared with everyone. When the project dependencies are installed, `Husky` ensures these shared hooks are properly set up locally.

## Key Automations Implemented
Here’s how I've configured automation in this project:
### 1. Pre-Commit Quality Checks (via `pre-commit` hook)
Before any code is actually committed, `Husky` triggers a series of automated checks:
* **Code Linting (e.g., with `ESLint`):** `ESLint` analyzes the JavaScript code to find potential errors, enforce coding standards, and identify stylistic issues. This helps catch bugs early and maintain code health.
* **Code Formatting (e.g., with `Prettier`):** `Prettier` automatically reformats the code to ensure a consistent visual style across the project (handling things like indentation, spacing, and line breaks). This improves readability.
* **Efficient Processing with `lint-staged`:** To ensure these pre-commit checks are fast and don't bog down the commit process, `lint-staged` is used. It intelligently runs the linters and formatters *only* on the files that have been staged for the current commit.
If any of these tools report errors that aren't automatically fixed, `Husky` will prevent the commit from completing, prompting me to address the issues first.
### 2. Commit Message Standardization (via `commit-msg` hook)
To maintain a clear, useful, and navigable commit history, I've used `commitlint`.
* This tool, triggered by `Husky` after I write a commit message but before the commit is finalized, checks if the message adheres to a specific convention (such as Conventional Commits, e.g., `feat: add new login button`).
* If the message format is incorrect, the commit is aborted, ensuring that all commit messages are structured consistently.
### 3. Continuous Integration (CI) with GitHub Actions
As an additional layer of quality assurance, I've configured a basic CI pipeline using **GitHub Actions**.
* This workflow automatically runs on GitHub's servers whenever code is pushed to the repository or a pull request is created.
* It typically executes tasks like installing dependencies and running the same linters (and could also include automated tests) to verify the code's integrity on a clean environment. This acts as a server-side safety net.

## Benefits of This Automated Workflow
Implementing these automations brings several significant advantages:
* **Improved Code Quality:** Reduces bugs and inconsistencies.
* **Enhanced Consistency:** Ensures all code and commit messages follow project standards.
* **Early Error Detection:** Catches issues locally before they become bigger problems or affect others.
* **Increased Productivity:** Automates repetitive checks, allowing developers to focus on core tasks.
* **Better Team Collaboration:** Makes the codebase easier to read, understand, and contribute to.
This setup demonstrates a more robust and professional approach to software development by integrating quality checks directly into the workflow.

##Setting up Husky
*** Step 1: Install Husky
* To install Husky, you need to run the following command in your project's root directory:
* Terminal
* npm install husky --save-dev

***Step 2: Enable Git hooks
* After installing Husky, you need to configure it to handle your Git hooks:
* Terminal
* npx husky install

***Step 3: Add hook scripts
* You can add Git hooks using Husky by creating a script in the .husky/ directory. For example, to add a pre-commit hook that runs linting before every commit, you could do the following:
* Terminal
* npx husky add .husky/pre-commit "npm run lint"
