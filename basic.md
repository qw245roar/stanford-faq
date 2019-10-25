To run Quickstart Jupyter Notebook locally using non-docker based installation, you will need to complete below steps.
1. Install NodeJS from here: https://nodejs.dev/how-to-install-nodejs
1. Install **Python 3.7 or newer** and Jupyter if you don't have them installed already. If you need to install pip separately you can do so from [here](https://pip.pypa.io/en/stable/installing/).
1. Install dependencies by running the below commands. You will need to run the commands within `bot-tutorial-master` folder which is the parent folder of this README.md. 
   You may need to use `sudo` for pip install commands.
    ```bash
    cd bot-tutorial-master
    pip install -e bot-sdk
    pip install -r requirements.txt
    jupyter labextension install @pyviz/jupyterlab_pyviz
    jupyter labextension install @jupyter-widgets/jupyterlab-manager
    ```
1. Load one of below Quickstart Jupyter Notebooks available in `bot-tutorial-master` folder.  We recommend that you start with Quickstart-Sine.
    * `Quickstart-Tutorial.ipynb`
    * `Quickstart-DTCC.ipynb`
1. Start JupyterLab by running below command:
    ```bash
    jupyter-lab
    ```

