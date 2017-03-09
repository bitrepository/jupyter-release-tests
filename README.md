# jupyter-release-tests
Jupyter notebooks for the release test


To use them, you must start a jupyter server.

## TL;DR install
```bash
sudo apt install virtualenvwrapper
sudo yum install python-virtualenvwrapper
echo 'export WORKON_HOME=$HOME/.virtualenvs' >> ~/.profile
echo 'mkdir -p $WORKON_HOME' >> ~/.profile
echo 'source  /usr/share/virtualenvwrapper/virtualenvwrapper.sh' >> ~/.profile
source ~/.profile
mkvirtualenv jupyterEnvironment -p /usr/bin/python3
pip install -U pip
pip install jupyter
pip install jupyter_contrib_nbextensions
jupyter contrib nbextension install --sys-prefix --symlink
jupyter nbextension enable contrib_nbextensions_help_item/main
jupyter nbextension enable execute_time/ExecuteTime
jupyter nbextension enable skip-traceback/main
jupyter nbextension enable tree-filter/index
jupyter nbextension enable codefolding/main
jupyter nbextension enable toc2/main
jupyter nbextension enable collapsible_headings/main
jupyter nbextension enable nbextensions_configurator/tree_tab/main
jupyter nbextension enable nbextensions_configurator/config_menu/main
jupyter nbextension enable init_cell/main
```

## TL;DR Run Jupyter
```bash
source ~/.profile
workon jupyterEnvironment
jupyter notebook
```


## The jupyter install procedure
1. To install the pythons virtualenv system on a ubuntu system, do
    ```bash
    sudo apt install virtualenvwrapper
    ```
    And on a Fedora System, do
    ```bash
    sudo yum install python-virtualenvwrapper
    ```

2. Then you must set up virtualenv
    Add this line to your ~/.bashrc or ~/.bash_profile or ~/.profile
    ```bash
    export WORKON_HOME=$HOME/.virtualenvs
    mkdir -p $WORKON_HOME
    source  /usr/share/virtualenvwrapper/virtualenvwrapper.sh
    ```

3. Start a new terminal (i.e. one that have the updated environment you just added)
    
4. Create a new virtual python environment (jupyterEnvironment is just a name I chose, you can pick another)
    ```bash
    mkvirtualenv jupyterEnvironment -p /usr/bin/python3
    pip install -U pip
    ```    
5. To switch to this new environment, use
    ```bash
    workon jupyterEnvironment
    ```    

6. To install jupyter in your new virtual python environment, do
    ```bash
    pip install jupyter
    ```
   
7. Install the jupyter extensions, as you want to be able to see table of contents and the like
    ```bash
    pip install jupyter_contrib_nbextensions
    jupyter contrib nbextension install --sys-prefix --symlink
    ```    
8. Enable the most nessesary extensions
    ```bash
    
    #An nbextension that renders the nbextensions configurator interface as a dashboard tab.
    jupyter nbextension enable nbextensions_configurator/tree_tab/main 

    #Add an edit-menu item to open the nbextensions configurator page
    jupyter nbextension enable nbextensions_configurator/config_menu/main 

    #The contrib_nbextensions_help_item is a tiny extension that just adds an item in the notebook's help menu, pointing to the jupyter_contrib_nbextensions at readthedocs.
    jupyter nbextension enable contrib_nbextensions_help_item/main
    
    #Display when each cell has been executed and how long it took
    jupyter nbextension enable execute_time/ExecuteTime

    #Don't display traceback, only error message
    jupyter nbextension enable skip-traceback/main

    #An extension that allows you to filter by filename in the Jupyter notebook file tree (aka dashboard) page.
    jupyter nbextension enable tree-filter/index

    #This extension enables the CodeMirror feature to allow codefolding in code cells
    jupyter nbextension enable codefolding/main

    #Allows notebook to have collapsible sections, separated by headings
    jupyter nbextension enable collapsible_headings/main
    
    #The toc2 extension collect all running headers and display them in a floating window, as a sidebar or with a navigation menu. 
    jupyter nbextension enable toc2/main
    
    #Add a cell toolbar selector to mark cells as 'initialization' cells. 
    jupyter nbextension enable init_cell/main
    ```
   
9. Then start jupyter and launch the notebooks
    ```bash
    jupyter notebook
    ```

To see what other extensions there are and configure them, go to http://localhost:8888/nbextensions
