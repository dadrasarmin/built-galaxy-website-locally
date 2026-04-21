This is the hands-on part for your journey. This is where all the tools (Conda, the Terminal, and Git) come together to show you the actual website they are helping to build. This is written based on [this tutorial](https://training.galaxyproject.org/training-material/topics/contributing/tutorials/rendering_gtn/tutorial.html).

---

# Topic 6: Building the Website Locally

The Galaxy Training Network (GTN) is a **Static Site**. This means it’s built from many small text files (Markdown) that are transformed into a website by a "generator" called **Jekyll**. 

By building it locally, you can see exactly what your new tutorial will look like in a browser before you send it to GitHub.

If you have not done it already, make a fork of the GTN repository. You may need to install a few tools first.

```bash
sudo apt update && sudo apt install git curl make
```

Then, create a local copy of it on your computer:

```bash
git clone --depth 1 --branch main https://github.com/galaxyproject/training-material.git
```
You need to do this step only once and from now on, you can just get the updates instead of all files.

You can create the conda environment and everything that is needed for GTN as follows:

If you do not have conda:

```bash
make install-conda
```

If you already have conda installed, you can create the conda environment as follows (it will be called `galaxy_training_material`):

```bash
make create-env
```

Finally, you need to install Jekyll and related modules into the conda environment:

```bash
make install
```
*Note: This might take a few minutes the first time. It's downloading all the "parts" of the website engine.* After the first time, you do not need to to this step.

---

After the first time everything is set for the future use.

## 1. Prepare Your Environment
First, make sure you are in your project folder and have your Conda "toolbox" active.

```bash
cd training-material
conda activate galaxy_training_material
```

---

## 2. The Magic Command: `make serve-quick HOST=127.0.0.1`
To start the website, run:

```bash
make serve-quick HOST=127.0.0.1
```

---

## 4. View Your Site
Once the terminal says `Server address: http://localhost:4000/training-material/`, your site is live!

1.  Open your web browser (Chrome, Firefox, etc.).
2.  Type **`http://localhost:4000/training-material/`** into the address bar and hit Enter.
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
