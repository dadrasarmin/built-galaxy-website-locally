This tutorial focuses on **Miniconda**, as it’s lightweight and generally preferred over the "heavy" Anaconda distribution.

# Topic 1: Checking for and Installing Conda

Conda is a **package manager** and **environment manager**. It helps you install software (like Ruby or Python) without messing up the rest of your computer.

-----

## 1\. Check if Conda is already installed

Before installing anything, let's see if your computer already has it. Open your **Terminal** (Mac/Linux) or **PowerShell/Command Prompt** (Windows) and type:

```bash
conda --version
```

  * **If it returns something like `conda 23.x.x`**: You are all set\! You can skip the rest of this guide.
  * **If it says "command not found"**: You need to install it. Follow the steps below for your specific operating system.

-----

## 2\. Installing Miniconda

We recommend **Miniconda** because it is small and only includes the essentials. There are other options such as Mamba, Anaconda, ... .

### Windows

1.  **Download:** Go to the [Miniconda Windows Installer page](https://www.anaconda.com/docs/getting-started/miniconda/install/overview) and download the **64-bit**.
2.  **Run:** Open the `.exe` file.
3.  **Crucial Step:** During installation, you will see a checkbox that says **"Add Miniconda3 to my PATH environment variable."** \* *Note:* The installer might say "not recommended," but for beginners, checking this makes it much easier to use Conda in your standard PowerShell.
4.  **Finish:** Click Install. Restart your terminal and try `conda --version` again.

### macOS

1.  **Download:** Download the "PKG" installer for your chip:
      * **Apple Silicon (M1/M2/M3):** Use the "Apple M1" version.
      * **Intel:** Use the "64-bit" version.
2.  **Install:** Follow the standard Mac installation prompts.
3.  **Verify:** Open the **Terminal** app and type `conda init`. Close the terminal and reopen it to finish the setup.

### Linux

1.  Open your terminal and run the following commands:
    ```bash
    wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
    bash Miniconda3-latest-Linux-x86_64.sh
    ```
2.  Follow the prompts (press **Enter**, type **yes** to the license, and **yes** to run `conda init`).
3.  Restart your terminal.

-----

## 3\. Pro-Tip: The "Base" Environment

Once installed, you might see `(base)` appear before your name in the terminal. This means Conda is active\!

> **Important:** We usually don't install things in the `base` environment. In the next tutorial, we will learn how to create "clean rooms" (environments) for different projects.
