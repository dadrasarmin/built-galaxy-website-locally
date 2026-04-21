# Topic 7: Building the Galaxy Hub Website (Astro)

The **Galaxy Hub** (the main community site at [galaxyproject.org](https://galaxyproject.org)) is built using **Astro**. While it looks similar to the GTN on the outside, it uses **Node.js** instead of Ruby under the hood.

---

## 1. Get the Code
The Hub code lives here: [https://github.com/galaxyproject/galaxy-hub](https://github.com/galaxyproject/galaxy-hub).

1.  **Fork** the repository on GitHub.
2.  **Clone** your fork to your computer:
    ```bash
    git clone https://github.com/YOUR-USERNAME/galaxy-hub.git
    cd galaxy-hub
    ```

---

## 2. Set Up the "Astro" Environment
Since Astro runs on **Node.js**, we need to tell Conda to give us a "toolbox" that includes it.

```bash
# Create a new environment for the Hub
# This installs Node.js and npm (the Node Package Manager)
conda create -n galaxy-hub nodejs=20 -c conda-forge

# Activate it
conda activate galaxy-hub
```

---

## 3. Install Dependencies
In the world of Node.js/Astro, we don't use `bundle install`. Instead, we use **`npm`**.

Inside your `galaxy-hub` folder, run:
```bash
npm install
```
*This reads the `package.json` file and downloads everything Astro needs to run.*

---

## 4. Launch the Preview
To start the local development server, run:

```bash
npm run dev
```

* **View the site:** By default, Astro uses a different "port" than Jekyll. Open your browser to **`http://localhost:4321`**.
* **Stop the site:** Press `Ctrl + C` in your terminal.

---

## Jekyll (GTN) vs. Astro (Hub) Reference

It's helpful to know the "translation" between these two systems:

| Feature | GTN (Jekyll) | Galaxy Hub (Astro) |
| :--- | :--- | :--- |
| **Language** | Ruby | Node.js (JavaScript) |
| **Install Command** | `bundle install` | `npm install` |
| **Run Command** | `bundle exec jekyll serve` | `npm run dev` |
| **Default Local URL**| `localhost:4000` | `localhost:4321` |
| **Configuration** | `_config.yml` | `astro.config.mjs` |

---

## 💡 Why the switch?
If you ask why they are different:
* **Jekyll** is older and very stable, great for the massive, documentation-heavy GTN.
* **Astro** is newer and much faster at loading pages, which is why the main "news and community" Hub uses it!

---

### Pro-Tip: The "Node Modules" Folder
When you run `npm install`, you will see a new folder appear called `node_modules`. This folder is **huge**. 
* **Never** add this folder to Git.
* The `.gitignore` file in the repository should already be hiding it, but it's good to know it's there!
