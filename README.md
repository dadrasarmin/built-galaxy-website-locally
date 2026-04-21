# GTN and Galaxy Hub Local Development: Quick Reference

Welcome\! Use this page as a "daily driver" for the commands you'll use most often.

## 1. The Daily Workflow

When you sit down to work on a tutorial, follow these steps in order:

| Step | Command | What it does |
| :--- | :--- | :--- |
| **1. Update** | `git pull upstream main` | Gets the latest GTN changes from the community. |
| **2. Prepare** | `conda activate galaxy_training_material` | Switches to your GTN "toolbox." |
| **3. Launch** | `make serve-quick HOST=127.0.0.1` | Starts the website locally at `http://localhost:4000/training-material/`. |
| **4. Save** | `git add .` then `git commit -m "My notes"` | Saves your progress to your "time machine." |
| **5. Upload** | `git push origin my-branch-name` | Sends your work to GitHub. |

-----

## Conda Essentials

| Goal | Command |
| :--- | :--- |
| **Enter environment** | `conda activate [name]` |
| **Exit environment** | `conda deactivate` |
| **See all my envs** | `conda env list` |
| **Install a tool** | `conda install [package] -c conda-forge` |
| **Reset environment** | `conda env create -f environment.yml` |

-----

## Git Essentials

| Goal | Command |
| :--- | :--- |
| **Check status** | `git status` (Do this often\!) |
| **Create new branch** | `git checkout -b [new-branch-name]` |
| **Undo last change** | `git restore [filename]` |
| **See history** | `git log --oneline` |

-----

## Build and Serve the Website

To see your changes, run this command in the root folder:

```bash
make serve-quick HOST=127.0.0.1
```

  * **View it at:** [http://localhost:4000/training-material/](http://localhost:4000/training-material/)
  * **Stop it with:** `Ctrl + C` (in the terminal)

-----

## 💡 Pro-Tips for Beginners

> **The Golden Rule:** If you get an error that says "Command not found," check if you are in the right folder (`ls`) and if your Conda environment is active.

> **Don't Panic:** If you make a mistake in Git, you haven't broken the internet. Ask for help, almost everything in Git can be "undone"\!

-----

### Navigation

  * [Introduction to Commandline](./00-command-line-basics.md)
  * [How to install Conda](./01-conda-setup.md)
  * [Managing Environments](./02-conda-environment-setup.md)
  * [Writing Bash Scripts](./03-bash-scripts.md)
  * [Git & GitHub](./04-git-and-version-control.md)
  * [VS Code](./05-vs-code.md)
  * [Building the GTN](./06-build-gtn-locally.md)
  * [Building the Galaxy Hub](./07-build-galaxy-hub-locally.md)
  * [Troubleshooting](./08-troubleshooting.md)
