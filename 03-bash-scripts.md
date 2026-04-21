Since the basics of Conda are clear, let’s move to **Topic 3**. This is where we start automating things. 

In the GTN, you’ll often find yourself running the same 3 or 4 commands every time you want to work. Instead of typing them manually, we put them in a "script."

---

# Topic 3: Writing Your First Bash Script

A **Bash script** is just a text file containing a list of commands. Your computer reads the file and runs the commands one by one, exactly as if you had typed them into the terminal yourself.

---

## 1. Create the File
1.  Open your text editor (like VS Code or notepad or whatever you like such as vim).
2.  Create a new file and name it `setup_gtn.sh`. 
    * *Note:* The `.sh` extension tells the computer "this is a shell script."

---

## 2. The "Shebang" (The First Line)
Every script should start with a special first line that tells the computer which "language" to use to read the file. For bash scripts, it looks like this:

```bash
#!/bin/bash
```

---

## 3. Adding Commands
Let's write a script that creates a folder, moves into it, and creates a "Welcome" file. Copy this into your `setup_gtn.sh`:

```bash
#!/bin/bash

# This is a comment (the computer ignores it)
echo "Starting the setup..."

# 1. Create a folder
mkdir my_gtn_project

# 2. Move into that folder
cd my_gtn_project

# 3. Create a simple text file
echo "Hello! This project was set up by a script." > welcome.txt

echo "Done! Check your new folder."
```

---

## 4. Making the Script "Executable" (Mac/Linux)
By default, your computer treats new files as "read-only" text for security. You have to give it permission to **run** the file as a program.

In your terminal, type:
```bash
chmod +x setup_gtn.sh
```
*(On Windows, if you are using Git Bash, this works the same way!)*



---

## 5. Running the Script
To run a script in your current folder, you type `./` followed by the filename:

```bash
./setup_gtn.sh
```

---

## 6. A Real GTN Example
When you start working on the Galaxy Training Network locally, your script might look like this to save you time:

```bash
#!/bin/bash

# Activate the toolbox we made in Lesson 2
conda activate gtn-env

# Start the local website server
bundle exec jekyll serve
```

---

### 💡 Troubleshooting for Beginners
* **"Permission Denied":** You forgot the `chmod +x` step.
* **"No such file or directory":** Make sure your terminal is "looking" at the same folder where you saved the script (use `ls` to check).
* **Windows Users:** If you aren't using Git Bash, bash scripts (.sh) won't run in standard PowerShell. I recommend using **Git Bash** (which comes with Git) to run these.
