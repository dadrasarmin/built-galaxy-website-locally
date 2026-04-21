**VS Code** is a good choice for managing your repositories and scripts. It’s the industry standard, and its integrated terminal will save them from the "window-switching fatigue" of jumping between a text editor and a separate terminal app.

---

# Topic 5: Setting Up VS Code

To build the GTN, you need a place to write code that isn't just a basic editor. You can definitely do it with vim, emacs or notepad, but it is easier with a modern IDE. **Visual Studio Code (VS Code)** is a powerful, free editor that makes it easy to see your files, write Markdown, and run terminal commands all in one window.

---

## 1. Installation
1.  **Download:** Go to [code.visualstudio.com](https://code.visualstudio.com/).
2.  **Install:** Follow the installer instructions for Windows, Mac, or Linux.
3.  **The "Path" Trick (Important):** * **Windows:** During installation, make sure to check the box that says **"Add to PATH (requires shell restart)."**
    * **Mac:** Open VS Code, press `Cmd + Shift + P`, type "shell command", and select **"Shell Command: Install 'code' command in PATH."**
    * *Why?* This allows you to open any folder from your terminal by just typing `code .`.

---

## 2. Essential Extensions (Completely optional and you can live without them)
VS Code is like a smartphone; it gets better with "apps" called Extensions. Click the **Extensions icon** (the 4 squares on the left sidebar) and install these:

| Extension | Why you need it |
| :--- | :--- |
| **GitHub Pull Requests** | Allows you to see and manage your GitHub work directly inside the editor. |
| **GitHub Actions** | GitHub Actions workflows and runs for github.com hosted repositories in VS Code |
| **GitHub Copilot Chat** | AI chat features powered by Copilot |
| **Python** | Python language support with extension access points for IntelliSense (Pylance), Debugging (Python Debugger), linting, formatting, refactoring, unit tests, and more. |

There are many more. Ask around and see what your colleagues are using and maybe you find new useful tools.

---

## 3. Opening Your Project
Instead of opening one file at a time, you should open the **entire folder**. It is called a project in VS Code.

1.  Open your terminal.
2.  Go to your GTN folder: `cd training-material`.
3.  Type: `code .`
4.  VS Code will open with the entire file tree on the left.

You can also do this via the Graphical menu on top. `File > Open Folder`.

---

## 4. The Integrated Terminal (Your Best Friend)
You don't need a separate Terminal window anymore! 

1.  In VS Code, go to the top menu: **Terminal > New Terminal** (or press ``Ctrl + ` ``).
2.  This opens a terminal at the bottom of your screen. 
3.  **Pro-Tip:** You can run your `conda activate galaxy_training_material` and `make serve-quick HOST=127.0.0.1` right here while you look at your code above it.

---

## 5. Working with Markdown (Completely optional. You can skip this!)
Since GTN tutorials are written in Markdown, use the **Built-in Preview**:
* Open a `.md` file.
* Press `Ctrl + Shift + V` (Windows/Linux) or `Cmd + Shift + V` (Mac).
* A split screen will open showing you exactly what the text will look like on the website.

---

## 6. Git inside VS Code
On the left sidebar, the third icon down (the "merge" symbol) is the **Source Control** tab.
* It shows you every file you’ve changed.
* Instead of typing `git add`, you can click the **+** sign next to a file.
* You can type your commit message in the box and click **Commit**.
* *Note: It is still good to learn the commands, but this is a great way to visualize what Git is doing!*

---

### The "Clean" Setup
To make your life easier, go to **File > Auto Save** and turn it on. This way, every time you type something, Jekyll will automatically detect the change and refresh your local website.
