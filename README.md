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
    *Source: PDF Page 4*
    ```
    ```

3.  **Conflict Markers in `index.html` (GitHub Conflict View):**
    *Description: This screenshot displays the `index.html` file within GitHub's conflict resolution interface, clearly showing the `<<<<<<< feature/add-content`, `=======`, and `>>>>>>> master` conflict markers.*
    *Source: PDF Page 6*
    ```
    ```

4.  **Successfully Resolved and Merged `feature/add-content` Pull Request (PR #2):**
    *Description: This screenshot shows the `feature/add-content` pull request (PR #2) page on GitHub after the conflict was resolved locally, pushed. It now indicates "No conflicts with base branch" and is ready to be (or has been) merged.*
    *Source: PDF Page 5*
    ```
    ```

---

## 🛠️ Brief Explanation of How the Conflict Was Resolved

The merge conflict encountered during this assignment was resolved through the following steps:

1.  **Identification:**
    * The conflict occurred in the `index.html` file.
    * It arose when attempting to merge the `feature/add-content` branch into `master` after the `feature/update-styling` branch (which also modified `index.html`) had already been merged.
    * Specifically, both branches modified the content of the `<h1>` tag. As seen in the conflict markers (PDF Page 6):
        * `feature/add-content` proposed: `<h1>Welcome to My Enhanced Page</h1>`
        * `master` (after `feature/update-styling` merge) had: `<h1>Welcome to My Updated Page</h1>` (Note: My previous example used "Awesome Page" for the first PR, your screenshot shows "Updated Page" which I am using now.)

2.  **Local Resolution Strategy (Assumed):**
    * *(Describe your local steps here. Since I don't have a screenshot of your local editor after fixing, I'm providing a template. Adjust as needed.)*
    * The `master` branch was checked out locally and updated with `git pull origin master`.
    * The `feature/add-content` branch was checked out.
    * The `master` branch was merged into `feature/add-content` locally using `git merge master`, triggering the conflict locally.
    * The `index.html` file was opened in a code editor.
    * The conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`) were identified.
    * **Decision:** *(Describe your decision, e.g., "I decided to keep the heading from the `feature/add-content` branch: `<h1>Welcome to My Enhanced Page</h1>`" or "I combined them to `<h1>Welcome to My Enhanced and Updated Page</h1>`" - **Adjust this to what you actually did to resolve it.**)*
    * The conflict markers were manually removed, leaving only the desired, resolved code.

3.  **Committing and Pushing the Resolution:**
    * The resolved `index.html` file was staged using `git add index.html`.
    * The resolution was committed with a descriptive message (e.g., `git commit -m "Resolve merge conflict in index.html"`).
    * The `feature/add-content` branch, now containing the resolved conflict, was pushed to the remote repository using `git push origin feature/add-content`.

4.  **Final Merge on GitHub:**
    * After pushing the resolved changes, the pull request for `feature/add-content` on GitHub (PR #2) updated, showing the conflict as resolved (as seen in PDF Page 5).
    * The pull request was then successfully merged into the `master` branch via the GitHub interface.

---

## ⚙️ Technology Stack

* **HTML5**
* **CSS3**
* **Git & GitHub**

---

## ✨ GitHub Flow Implementation

This repository demonstrates the GitHub Flow through the following steps:

1.  The `master` branch (as named in your repository) was kept as the primary stable branch.
2.  New work was started on feature branches (`feature/update-styling`, `feature/add-content`) branched off `master`.
3.  Commits were made locally and pushed to remote feature branches.
4.  Pull Requests were opened on GitHub for each feature branch.
5.  The first feature branch (`feature/update-styling`) was merged into `master`.
6.  The second feature branch (`feature/add-content`) resulted in a merge conflict with `master`.
7.  The conflict was resolved locally, and the changes were pushed to `feature/add-content`.
8.  The updated `feature/add-content` branch was then merged into `master` via its Pull Request.

This process ensured that `master` was updated in a controlled manner.

---
