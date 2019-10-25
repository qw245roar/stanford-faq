# Run the Quickstart Notebooks from Jupyter without Docker
To run Quickstart Jupyter Notebook locally using non-docker based installation, you will need to complete below steps.
1. Install NodeJS from here: https://nodejs.dev/how-to-install-nodejs
1. Install **Python 3.7 or newer** and Jupyter if you don't have them installed already. If you need to install pip separately you can do so from [here](https://pip.pypa.io/en/stable/installing/).
1. Install dependencies by running the below commands. You will need to run the commands within `bot-tutorial-master` folder which is the parent folder of this README.md. 
   You may need to use `sudo` for pip install commands.
    ```bash
    cd bot-tutorial-master
    ./scripts/local_install.sh
    ```
1. Load one of Quickstart Jupyter Notebooks provided in `bot-tutorial-master` bundle.  
1. Start JupyterLab by running below command:
    ```bash
    jupyter-lab
    ```

