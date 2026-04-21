This is the hands-on part for your journey. This is where all the tools—Conda, the Terminal, and Git—come together to show you the actual website they are helping to build.

---

# Topic 6: Building the Website Locally

The Galaxy Training Network (GTN) is a **Static Site**. This means it’s built from many small text files (Markdown) that are transformed into a website by a "generator" called **Jekyll**. 

By building it locally, you can see exactly what your new tutorial will look like in a browser before you send it to GitHub.

---

## 1. Prepare Your Environment
First, make sure you are in your project folder and have your Conda "toolbox" active.

```bash
cd training-material
conda activate gtn-env
```

---

## 2. Install the "Gems"
Jekyll uses "Gems" (small pieces of Ruby code) to function. We use a tool called **Bundler** to manage them. Run this command to install everything the GTN needs:

```bash
bundle install
```
*Note: This might take a few minutes the first time. It's downloading all the "parts" of the website engine.* After the first time, you do not need to to this step.

---

## 3. The Magic Command: `jekyll serve`
To start the website, run:

```bash
bundle exec jekyll serve --incremental --limit_posts 10
```

### What do these flags mean?
* **`bundle exec`**: Tells the computer to use the specific versions of tools we just installed.
* **`jekyll serve`**: Starts a mini-web server on your laptop.
* **`--incremental`**: Only rebuilds the pages you change (much faster!).
* **`--limit_posts 10`**: The GTN is huge. This tells Jekyll to only build a small part of it so it doesn't take 20 minutes to start.

---

## 4. View Your Site
Once the terminal says `Server address: http://127.0.0.1:4000/`, your site is live!

1.  Open your web browser (Chrome, Firefox, etc.).
2.  Type **`localhost:4000`** into the address bar and hit Enter.
3.  You are now browsing the GTN from your own hard drive!

---

## 5. The "Edit-Refesh" Loop
This is the best part of local development:

1.  Keep the terminal (or VS Code) running.
2.  Open a Markdown file in your text editor (VS Code) and change a sentence.
3.  Save the file.
4.  Watch your terminal—it will say "Regenerating..."
5.  Refresh your browser. **Your changes appear instantly!**

---

## 6. Shutting Down
When you are done working:
1.  Go to the terminal.
2.  Press **`Ctrl + C`** on your keyboard. This stops the server.
3.  Type `conda deactivate` to put your tools away.

---

### Troubleshooting
* **"Address already in use":** You probably have another version of the site running in a different terminal window. Close it and try again.
* **"Bundle command not found":** Make sure you are in the correct Conda environment where Ruby/Jekyll are installed.
