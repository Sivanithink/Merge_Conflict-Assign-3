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


