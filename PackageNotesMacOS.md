# MAC OS Package Notes for PyCity School District
This file has installation and set up instructions to ensure the dev env is set up properly to use Anaconda and Jupyter. Resolutions to errors that were not covered in the coursework are covered here as well.

## 4.1.1 - Overview of Anaconda
- Anaconda: Open source distribute software
- Contains packages that support Python and R programming
- Jupiter Notebook: Product distributed by Anaconda.
   - Allows you to create docs containing live code using languages such as Python.
   - It is to Anaconda what MS Word is to MS Office
 - Mac Installation Notes: 
   - check installation with ```conda --version```
   - conda is the package management system for Anaconda
   - If conda version is < 4.8 v. run: ```conda update conda```
      - Enter ```y``` when prompted
      - run ```conda update Anaconda```

## 4.1.2 Introduction to Jupyter Notebook
- IDE Web based app for sharing docs with live code, equations, charts, graphs and text info
- The following tasks can be performed:
   - Import data from many different formats
   - Clean data
   - Merge similar datasets
   - Filter based on conditionals
   - Slice on ranges
   - Sort based on values
   - Group data into similar categories
   - Visualize data
   - Write SQL queries
   - Stats analysis
  
## 4.2.1 Create a Dev Env[^1]
- The dev env is a virtual environment to allow developers to work with different versions of packages required for the application or system.
- For this project, we need to use Python version 3.7.6.
- Enter ```conda create -n PythonData python=3.7.6 anaconda``` to create a new virtual dev env named "PythonData"
- In the above command, 'anaconda' adds the appropriate packages for the version of python specified
- Enter ```y``` when prompted
- Enter ```conda activate PythonData```
- To see all dev envs enter ```conda info --envs```.
- There should be at least 2 envs, "base" and "PythonData"

## 4.2.2 Activate Dev Env[^2]
- Follow these steps to ensure we are in the right env
   - ```python --version``` 
   - If the previous command did not return 3.7.6, then delete the current PythonData env as follows:
      - ```conda deactivate```
      - ```conda env remove --name PythonData```
   - Follow the steps in 4.2.1 to create the env for the correct version
   - Enter ```conda activate PythonData``` to activate the PythonData env
  
## 4.2.2 Create and Clone a New GitHub Repo
 
### Create a repo with GitHub as follows
- Add repo name
- Add Description (optional as this will be added in the Readme.md file later)
- Make the repo public
- Init with a Readme
- Add .gitignore and type "Python"
- Create Repo
- Before cloning, add ".DS_Store" to .gitignore to protect info to your computer.
- Follow these steps from the CLI for any repos cloned before .gitignore was modified to ignore .DS_Store:
   - Launch terminal
   - Create a .gitignore file in the folder of the repo
   - Add ".DS_Store" to .gitignore and save using a text editor such as vi or nano
   - Remove the .DS_Store file from the repo and update it from the CLI as follows:
     ```
     $ find . -name .DS_Store -print0 | xargs -0 git rm -f --ignore-unmatch
     $ git status
     $ git add .gitignore
     $ git commit -m 'Removes all .DS_Store files from repo and ignores them going forward.'
     $ git push
     ```
- From the GitHub webpage, navigate to the repo created above.
- Click the green "Clone or download box and select HTTPS and copy the URL for the repo

### Clone a Repo from CLI
From the terminal do the following:
- Navigate to the folder where the repo should be cloned and enter 
  ```$ git clone https://github.com/<github_account>/School_District_Analysis.git```
- Where the https path is the path copied from the repo earlier.
- Press enter to clone the repo
- If prompted, enter username and password for GitHub[^3]
- Once the repo has been cloned, there should be a folder with the same name as the repo

## 4.3.1 Starting Jupyter Notebook Server

### Add Dev Env to Jupyter Notebook
- In Terminal, enter ```python -m ipykernel install --user --name PythonData```
- The instructions state that ```Installed kernelspec PythonData in \Users\<your computer name>\AppData\Roaming\jupyter\kernels\PythonData``` should be printed to the terminal, however, it actually installed PythonData in ```/Users/<your computer name>/Library/Jupyter/kernels/PythonData```
- If Chrome is not the default browser, enter ```jupyter notebook --browser chrome``` to open the Jupyter notebook in Chrome.
- Add .ipynb_checkpoints to .gitignore

     
### Footnotes:
[^1]: See video for this module to see the output from these steps
[^2]: Always deactivate the current dev env before updating Anaconda as a best practice
[^3]: If a username and password is required it is possible that it will not work and an error will indicate that it is not authorized. To fix this, a personal access token needs to be generated and copied to a safe location. Use this key instead of password to log in from the CLI.
