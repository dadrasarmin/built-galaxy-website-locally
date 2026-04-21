This is arguably the most important "superpower" of Conda. For the a tool or service such as Galaxy Training Network, we often need specific versions of Ruby or Python that might clash with other projects on your computer. Environments solve this perfectly.

---

# Topic 2: Managing Environments, Packages, and Channels

Think of a **Conda Environment** like a "clean room" or a specialized "toolbox" for a specific project. You can have one toolbox for the Galaxy website (with Ruby) and another for data analysis (with Python), and they will never interfere with each other.

---

## 1. Creating Your First Environment
To create a new environment, use the `create` command. We use the `-n` flag to give it a **name**.

```bash
conda create -n gtn-test
```
*Conda will ask if you want to proceed. Type `y` and hit Enter.*



---

## 2. Activating and Deactivating
Creating the environment doesn't mean you are "inside" it yet. You have to **activate** it.

* **To enter:** `conda activate gtn-test`
* **To leave:** `conda deactivate`

> **Note:** Your terminal prompt will usually change from `(base)` to `(gtn-test)` to show you where you are.

---

## 3. Installing Packages
Once your environment is active, you can install software (packages).

```bash
conda install wget
```

### Specifying Versions
Sometimes a project only works with an older version of a tool. You can force Conda to install a specific version using the `=` sign.

```bash
conda install python=3.9
```

---

## 4. Understanding Channels (The "App Stores")
Conda doesn't keep all software in one giant pile. It uses **Channels**, which are like different app stores. 

* **Default:** The standard store provided by Anaconda. Due to licensing reasons, I highly recommend to NOT user the default. Always specify the channel that you are using to download the tools.
* **Conda-forge:** A massive, community-led store. **For GTN and bioinformatics, we almost always use this.**
* **Bioconda:** Specialized for biology and bioinformatics tools.

### How to use a channel
Use the `-c` flag to tell Conda which "store" to look in:

```bash
conda install jekyll -c conda-forge
```
*This tells Conda: "Install Jekyll, but look for it in the conda-forge store."*

---

## 5. Putting it All Together (The Pro Way)
You can create an environment, specify a version, and choose a channel all in one single command:

```bash
conda create -n gtn-env python=3.10 ruby=3.2 -c conda-forge
```

---

## 6. How to see what you have
If you forget what environments you've made or what is inside them, use these:

* **List all environments:** `conda env list`
* **List all packages in current env:** `conda list`
* **Delete an environment you don't need:** `conda env remove -n gtn-test`

---

### 💡 GTN Tip
When building the Galaxy Training Network locally, we can use a file that usually called `environment.yml` (but could be called something else as well). Instead of typing commands one by one, you just run:
`conda env create -f environment.yml`
This automatically builds the exact "toolbox" needed for the website!
