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
jupyter nbextension enable toc2/main
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
8. Enable the TableOfContents extension
    ```bash
    jupyter nbextension enable toc2/main
    ```
   
9. Then start jupyter and launch the notebooks
    ```bash
    jupyter notebook
    ```

To see what other extensions there are and configure them, go to http://localhost:8888/nbextensions
