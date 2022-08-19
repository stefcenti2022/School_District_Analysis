# Package Notes for PyCity School District

## 4.1.1 - Overview of Anaconda
- Anaconda: Open source distribute software
- Contains packages that support Python and R programming
- Jupiter Notebook: Product distributed by Anaconda.
   - Allows you to create docs conteaing live code useing languages such as Python.
   - It is to Anaconda what MS Word is to MS Office
 - Mac Installation Notes: 
   - check installatioin with ```conda --version```
   - conda is the package mangement system for Anaconda
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
   - Stats analyis
  
## 4.2.1 Create a Dev Env[^1]
- The dev env is a virtual environment to allow developers to work with different versions of packages required for the application or system.
- For this project, we need to use Python version 3.7.6.
- Enter ```conda create -n PythonData python=3.7.6 anaconda``` to create a new virtual dev env named "PythonData"
- In the above command, 'anaconda' adds the appropriate packages for the verion of python specified
- Enter ```y``` when prompted
- To see all dev envs enter ```conda info --envs```.
- There should be at least 2 envs, "base" and "PythonData"

## 4.2.2 Activate Dev Env[^2]
- Follow these steps to ensure we are in the right env
   - python --verion 
   - If the previous command did not return 3.7.6, then delete the current PythonDta env as follows:
      - ```conda deactivate```
      - ```conda env remove --name PythonData```
   - Follow the steps in 4.2.1 to create the env for the correct verstion
   - Enter ```conda activate PythonData``` to activate the PythonData env
  
 ## 4.2.2 Create and Clone a New GitHub Repo
 - Create a repo with GitHub as follows:
    - Add repo name
    - Add Description (optional as this will be added in the Readme.md file later)
    - Make the repo public
    - Init with a Readme
    - Add .gitignore and type "Python"
    - Create Repo
  - Before cloning, add ".DS_Store" to .gitignore to protect info to your computer.
  - Follow these steps fromt the CLI for any repos cloned before .gitignore was modified to ignore .DS_Store:
      - Create a .gitignore file in the directory of the repo
      - Add ".DS_Store" to .gitignore and save using a text editor such as vi or nano
      - Remove the .DS_Store file from the repo and update it from the CLI as follows:
        ```
        $ find . -name .DS_Store -print0 | xargs -0 git rm -f --ignore-unmatch
        $ git status
        $ git add .gitignore
        $ git commit -m 'Removes all .DS_Store files from repo and ignores them going forward.'
        $ git push
        ```
         
     
  
### Footnotes:
[^1]: See video for this module to see the output from these steps
[^2]: Always deactivate the current dev env before updating Anaconda as a best practice
