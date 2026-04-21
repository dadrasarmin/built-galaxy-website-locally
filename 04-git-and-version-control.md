# Topic 4: Version Control with Git and GitHub

Git is a "time machine" for your code. It tracks every change you make, allowing you to go back in time if you break something. **GitHub** is the website where we store that "time machine" online so others can see it and collaborate. There are other software or tools such as GitLab that are available as alternative to GitHub.

---

## 1. The Big Picture: How we collaborate
In the Galaxy Training Network (GTN), we use a "Fork and Pull Request" workflow. It looks like this:

1.  **Fork:** You make a personal copy of the GTN project on GitHub.
> This is neccessary only once. After the first time, you just need to update your fork with the latest changes of the original repository.
2.  **Clone:** You download your copy to your computer.
> After the first time that you download a repository, you do now need to download it again each time. You can just download the latest updates from GitHub. We cover that leter.
3.  **Branch:** You create a "side-track" for your specific changes.
> It is highly recommended to not perform changes on your main (sometimes called master) branch. For each development, create a new branch and when you are completely done with it, you can clean them every now and then.
4.  **Commit:** You save your progress.
5.  **Push:** You send your saves back up to GitHub. In this step, you send you changes to YOUR OWN fork of the repository. You have to take another step to integrate your suggestions into the main repository.
6.  **Pull Request (PR):** You ask the GTN team to merge your "side-track" into the main project. They may provide some feedback and request some changes.



---

## 2. Basic Setup
First, tell Git who you are (do this once):

```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

---

## 3. The "Edit" Workflow (Step-by-Step)

### Step A: Forking
Go to the [GTN GitHub Repository](https://github.com/galaxyproject/training-material) and click the **Fork** button in the top right. This creates a copy under your account.

### Step B: Cloning
Copy the URL of **your** fork and type this in your terminal:
```bash
git clone --depth 1 --branch main https://github.com/galaxyproject/training-material.git
cd training-material
```
Note: The GTN repo is quite large, therefore we recommend to use the `--depth 1 --branch main` flags here. This will clone only the main branch, and only the most recent revision, rather than the full history.

### Step C: Creating a Branch
Never work directly on the `main` branch. Always create a new one for your specific task (e.g., a new tutorial).
```bash
git checkout -b add-my-new-tutorial
```
*The `-b` stands for "new branch".* If you have already a branch you will do:
```bash
git checkout whatever-branch-name-is
```

---

## 4. Saving Your Work
Once you have edited some files in your text editor, you need to "save" them to Git. This is a two-step process:

1.  **Stage (Add):** Tell Git which files you want to save.
    ```bash
    git add filename.md
    ```
2.  **Commit:** Actually save them with a descriptive note.
    ```bash
    git commit -m "Add initial draft of the new tutorial"
    ```



---

## 5. Sending it to GitHub (Push)
Your commits are currently only on your computer. To send them to GitHub, use:
```bash
git push origin add-my-new-tutorial
```
Here, `origin` tells git that it should go to the original repository (here it is your fork that you downlaoded). Also, `add-my-new-tutorial` is the name of the branch that you want to add to your `origin` repository.

---

## 6. The Pull Request (PR)
1.  Go to your repository page on GitHub.com.
2.  You will see a yellow bar that says **"Compare & pull request."** Click it.
3.  Write a description of what you did and click **"Create pull request."**

---

## Summary of Commands

| Command | What it does |
| :--- | :--- |
| `git status` | Shows what files you have changed. **Use this constantly!** |
| `git log` | Shows the history of your "saves" (commits). |
| `git pull` | Downloads the latest changes from GitHub to your computer. |
| `git diff` | Shows the exact lines of code you changed. |

---

> **Pro-Tip for GTN:**
> If you are working on a tutorial and someone else updates the GTN, your local copy might get out of date. We use `git pull upstream main` to keep our work synced with the community. There are other ways to do this as well. Generally, I suggest to you to `pull` before start changing things and then `push`.
