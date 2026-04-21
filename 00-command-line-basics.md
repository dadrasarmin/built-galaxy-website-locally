# Topic 00: Command Line Basics

The **Terminal** (also called the Command Line or CLI) is just a way to talk to your computer using text instead of clicking icons. Everything you do with a mouse opening folders, moving files, creating shortcuts can be done here faster.

---

## 1. Where am I? (`pwd` and `ls`)
When you open the terminal, you are always "inside" a folder. 

* **`pwd` (Print Working Directory):** Shows you the full path of where you are currently standing.
* **`ls` (List):** Shows you all the files and folders inside your current location.
    * *Pro-Tip:* Try `ls -F`. It adds a `/` to the end of folder names so you can tell them apart from files!

---

## 2. Moving Around (`cd`)
To move between folders, we use the **`cd`** (Change Directory) command.

| Command | Where it takes you |
| :--- | :--- |
| `cd Documents` | Moves **into** the Documents folder. |
| `cd ..` | Moves **up** one level (out of the current folder). |
| `cd ~` | Moves back to your **Home** folder (your user profile). |
| `cd -` | Moves back to the **previous** folder you were just in. |

> **Beginner Mistake:** You can't `cd` into a file (like a `.md` or `.txt` file). You can only `cd` into folders!

---

## 3. Managing Files and Folders
| Action | Command | Example |
| :--- | :--- | :--- |
| **Create a Folder** | `mkdir [name]` | `mkdir my-new-tutorial` |
| **Create a File** | `touch [name]` | `touch intro.md` |
| **Copy a File** | `cp [old] [new]` | `cp intro.md backup.md` |
| **Move/Rename** | `mv [old] [new]` | `mv intro.md final.md` |
| **Delete (CAUTION)**| `rm [name]` | `rm temporary_file.txt` |

**Warning:** There is no "Trash Can" or "Recycle Bin" in the terminal. When you `rm` a file, it is gone forever. Use it carefully!

---

## 4. The Two "Magic" Keys
To look like a pro and avoid typos, use these two keys constantly:

1.  **The Tab Key (Autocomplete):** Start typing a folder name (like `cd trai...`) and hit **Tab**. The computer will finish the word for you. If it doesn't finish, you probably made a typo!
2.  **The Up Arrow (History):** Don't re-type long commands. Hit the **Up Arrow** on your keyboard to scroll through the last few commands you ran.

---

## 5. Cleaning Up
If your terminal window gets too messy with text and you want a fresh start, type:
```bash
clear
```
*This doesn't delete your work; it just scrolls the old text out of view.*

---

## How this helps with GTN
When you work on the Galaxy Training Network, you will use these commands to find your tutorial:
1. `cd training-material` (Enter the project)
2. `ls topics/` (See all the different subjects)
3. `cd topics/sequence-analysis/tutorials/` (Find a specific tutorial)

---

### One Final Tip: Paths with Spaces
If a folder name has a space (like `My Projects`), you must put it in quotes or the terminal will get confused:
`cd "My Projects"`
