# Topic 7: Building the Galaxy Hub Website (Astro)

The **Galaxy Hub** (the main community site at [galaxyproject.org](https://galaxyproject.org)) is built using **Astro**. While it looks similar to the GTN on the outside, it uses **Node.js** instead of Ruby under the hood. This documentn is based on [this file](https://github.com/galaxyproject/galaxy-hub/blob/main/CONTRIBUTING.md).

---

## 1. Get the Code
The Hub code lives here: [https://github.com/galaxyproject/galaxy-hub](https://github.com/galaxyproject/galaxy-hub).

1.  **Fork** the repository on GitHub.
2.  **Clone** your fork to your computer:
    ```bash
    git clone --depth 1 --branch main https://github.com/YOUR-USERNAME/galaxy-hub.git
    cd galaxy-hub
    ```

---

## 2. Set Up the "Astro" modules
Since Astro runs on **Node.js**, we need to install a couple of tools.

```bash
make dev
```

*This reads the `package.json` file and downloads everything Astro needs to run, when it is executed for the first time. Aftere that it takes really less time to check.*
* **View the site:** By default, Astro uses a different "port" than Jekyll. Open your browser to **`http://localhost:4321`**.
* **Stop the site:** Press `Ctrl + C` in your terminal.

Before opening a PR, run:
```
make content-lint
make validate-metadata
```

Note: The dev server is case-insensitive for URLs but production is case-sensitive. Always use lowercase URLs.

Sometimes, someone tell you that you have to `build` the website to see the changes. You can do that as follows:
```bash
npm run build        # full production build
npm run preview      # serve the built site locally
```

---

### Pro-Tip: The "Node Modules" Folder
When you run `npm install`, you will see a new folder appear called `node_modules`. This folder is **huge**. 
* **Never** add this folder to Git.
* The `.gitignore` file in the repository should already be hiding it, but it's good to know it's there!
