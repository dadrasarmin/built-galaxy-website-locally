# Topic 7: Troubleshooting & Common Errors

Building software locally can be "finicky." If you see a wall of red text in your terminal, **don't panic.** Most errors in the GTN setup fall into one of these categories.

---

## 1. "Command Not Found"
**The Error:** `bash: jekyll: command not found` or `conda: command not found`.

* **The Cause:** Your terminal doesn't know where the tool is.
* **The Fix:** * Did you activate your environment? Run `conda activate gtn-env`.
    * If it’s `conda` itself that is missing, you might need to restart your terminal or run `source ~/.bashrc` (Linux) or `source ~/.zshrc` (Mac).

---

## 2. "Permission Denied"
**The Error:** `-bash: ./setup_gtn.sh: Permission denied`.

* **The Cause:** You’re trying to run a script, but the computer thinks it’s just a text file.
* **The Fix:** Run the change-mode command to make it executable:
    ```bash
    chmod +x your_script_name.sh
    ```

---

## 3. "Address already in use" (Port 4000)
**The Error:** `Address already in use - bind(2) for "127.0.0.1" port 4000`.

* **The Cause:** You likely have another Jekyll server running in a different terminal tab, or you didn't close the previous one properly.
* **The Fix:**
    * Find the other terminal and press `Ctrl + C`.
    * **The "Nuclear" Fix:** If you can't find it, you can force-kill whatever is using that port:
        * *Mac/Linux:* `fuser -k 4000/tcp`
        * *Windows (PowerShell):* `Stop-Process -Id (Get-NetTCPConnection -LocalPort 4000).OwningProcess`

---

## 4. Ruby Version Mismatch
**The Error:** `Your Ruby version is X, but your Gemfile requires Y`.

* **The Cause:** This usually happens when you are using the version of Ruby that came with your Mac/Linux instead of the one inside your Conda environment.
* **The Fix:** 1.  Check which Ruby you are using: `which ruby`.
    2.  If it says `/usr/bin/ruby`, you aren't in your Conda env.
    3.  Run `conda activate gtn-env` and try again.

---

## 5. Git Merge Conflicts
**The Error:** `CONFLICT (content): Merge conflict in index.md. Automatic merge failed; fix conflicts and then commit the result.`

* **The Cause:** You and someone else changed the **exact same line** in the same file. Git doesn't know which version to keep.
* **The Fix:**
    1.  Open the file in VS Code.
    2.  Look for the weird symbols: `<<<<<<< HEAD` and `>>>>>>>`.
    3.  Delete the version you don't want and remove the symbols.
    4.  Save, then run `git add .` and `git commit`.

---

## Troubleshooting Table

| If you see... | Try this... |
| :--- | :--- |
| `Could not find a JavaScript runtime` | Install Node.js: `conda install nodejs -c conda-forge` |
| `Bundle install fails` | Delete the `Gemfile.lock` file and try `bundle install` again. |
| `Git: "Not a git repository"` | Make sure you `cd` into the `training-material` folder first. |
| `Changes not showing in browser` | Check if your terminal says "Regenerating...". If not, restart Jekyll. |

---

> **Pro-Tip:** If you get an error you've never seen before, **Copy and Paste the last line of the error into Google.** Chances are, a thousand people have had the same problem and the fix is on Stack Overflow!
