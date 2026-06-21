# Local Environment Setup Guide

This guide sets up your computer to run the MFRE Welcome Package materials. Part 1 covers Python (Anaconda, VS Code, Jupyter). Part 2 covers R (R, RStudio, and the packages used in the R notebooks).

Work through Part 1 for the Python notebooks and Part 2 for the R notebooks. If you get stuck, note the step and the exact error message, and we will help during the first week of the bootcamp.

---

# Part 1: Python

## Step 1: Install Anaconda

1. Go to https://www.anaconda.com/download
2. Download the installer for your operating system (Windows, macOS, or Linux), Python 3.x version.
3. Run the installer and keep the default options unless you know you need to change them.
4. To confirm it worked, open the Anaconda Prompt (Windows) or a terminal (macOS/Linux) and run:

   ```
   conda --version
   ```

   You should see a version number.

## Step 2: Install VS Code

1. Go to https://code.visualstudio.com and download the installer for your operating system.
2. Run the installer, then launch VS Code.
3. Open the Extensions panel and install:
   - Python (by Microsoft)
   - Jupyter (by Microsoft)

## Step 3: Create a Python environment

A separate environment keeps the packages for this course isolated from the rest of your system.

1. Open the Anaconda Prompt (Windows) or a terminal (macOS/Linux).
2. Create the environment:

   ```
   conda create -n mfre python=3.10
   ```

3. Activate it:

   ```
   conda activate mfre
   ```

4. Install the packages the notebooks use:

   ```
   conda install jupyter pandas numpy matplotlib
   ```

Activate this environment (`conda activate mfre`) every time you work on the Python notebooks.

## Step 4: Run a Jupyter notebook

**Option A: Anaconda Navigator**

1. Launch Anaconda Navigator.
2. Click Launch under Jupyter Notebook.
3. In the browser tab that opens, navigate to the welcome package folder and click a `.ipynb` file.

**Option B: Terminal**

1. Activate the environment and move to the notebook folder:

   ```
   conda activate mfre
   cd path/to/welcome_package/python
   ```

2. Start Jupyter:

   ```
   jupyter notebook
   ```

3. Click a `.ipynb` file in the browser tab that opens.

---

# Part 2: R

The R notebooks (`.Rmd` files) need two programs: **R** (the language) and **RStudio** (the editor used to run and knit `.Rmd` files). Install R first, then RStudio.

## Step 5: Install R

1. Go to https://cran.r-project.org
2. Choose your operating system:
   - **Windows**: click "Download R for Windows", then "base", then "Download R for Windows", and run the installer.
   - **macOS**: click "Download R for macOS" and choose the `.pkg` that matches your chip (Apple Silicon or Intel). If unsure, check the Apple menu > About This Mac.
   - **Linux**: follow the instructions for your distribution.
3. Run the installer and keep the default options.

## Step 6: Install RStudio

1. Go to https://posit.co/download/rstudio-desktop
2. Download RStudio Desktop (free) for your operating system and run the installer.
3. Open RStudio. It finds your R installation automatically. In the bottom-left Console you should see the R version printed at startup.

## Step 7: Install the R packages

The R notebooks use a few packages. Install them once. In the RStudio Console, type:

```r
install.packages(c("rmarkdown", "zoo", "class", "ggplot2"))
```

Press Enter and wait for the downloads to finish. If you are asked to choose a CRAN mirror, pick any one near you.

Note: `r_applications.Rmd` also installs `zoo`, `class`, and `ggplot2` automatically the first time you knit it, if they are missing. Installing them here first means the first knit is faster and does not need to download anything.

## Step 8: Open and run an R Markdown file

1. In RStudio, choose File > Open File and select an `.Rmd` file (start with `r/r_intro.Rmd`).
2. To render the whole document, click the **Knit** button in the toolbar. RStudio runs every cell in order and produces an HTML file.
3. To run a single cell while you read, click inside it and press `Ctrl + Enter` (`Cmd + Enter` on macOS).

If knitting prompts you to install a missing package, accept and let it install, then knit again.

---

# Tips

- Activate your Python environment before working on the notebooks:

  ```
  conda activate mfre
  ```

- Update Python packages when needed:

  ```
  conda update --all
  ```

- Deactivate the Python environment when you are done:

  ```
  conda deactivate
  ```

# Questions

If you hit a problem during setup, write down the step and the exact error message. We will go over common setup issues at the start of the bootcamp.
