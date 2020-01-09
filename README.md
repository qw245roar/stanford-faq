# Welcome
If you are reading this README it means you have downloaded `bot-tutorial-master` bundle from the [ROAR Getting Started](https://web.stanford-roar.com/#/guide) page.  You will need to complete below prerequisite steps before you can enter your bot model in a ROAR contest using one of the provided Jupyter Notebooks in this bundle. 

## Prerequisites

### Obtain a Bot Identity Token
Before you can connect to a ROAR contest via one of the provided Quickstart Jupyter Notebooks, you will need complete below steps to register your bot in the contest you wish to enter.
1. Launch the [ROAR web application](https://stanford-roar.com) and log in. 
1. Click *View & Enter Your Bots* button to the right of the contest you wish to enter your bot in and follow the bot creation wizard.
1. Use *COPY TOKEN* button to put the identity token generated for your bot in the Clipboard.


### Review Contest Description
Make sure to review the Contest Description page for the contest in which you want to enter your bot model.  You can find it by browsing the [ROAR Contests](https://web.stanford-roar.com/#/contests) view and clicking the *Read Description* button to the right of the contest name. For DTCC contest, please review below additional resources from the `bot-tutorial-master` bundle: 
- `protocol.md`: Covers the raw protocol for question and prediction messages in the DTCC contest  
- `DTCC-Data-Exploration.ipynb`: provides historic DTCC trade data (the live data stream is also exposed via `on_broadcast` method in the  Quickstart Jupyter notebooks listed below), and also offers examples of applying different machine learning models to the DTCC data.  Note this data covers all indices, not just the four you are asked to predict for DTCC contest.

## Quickstart Jupyter Notebooks
In the downloaded `bot-tutorial-master` bundle you will find below Quickstart Jupyter Notebooks which you can use to build a model and enter your bot into either of the two contests hosted on ROAR (namely Tutorial/Sine and DTCC).
- `Quickstart-Beginner.ipynb` <br/>
  This quickstart uses a last value model to predict the target for a contest in ROAR.
- `Quickstart-Intermediate.ipynb` <br/>
  This quickstart uses a linear regression model to predict the target for a contest in ROAR.
- `Quickstart-Advanced.ipynb` <br/>
  This quickstart uses a temporal convolutional network model to predict the target for a contest in ROAR.
  
    
### Running Notebooks and Bots Locally
**Caution**: A locally-deployed model will only run when your computer is awake and has internet connection. For a bot to participate in the online contest for extended period of time see the JupyterHub section below.

The steps in this section describe how to set-up Python and JupyterLab environment on
your local workstation or laptop. The instructions are specific for Mac and Linux OS, 
but with small tweaks can be made to work for Windows.

1. **NodeJS** LTS version (e.g. 8, 10, 12) is required by Jupyter and can be installed from  https://nodejs.dev/how-to-install-nodejs
1. **Python 3.7** is required and install can be installed from https://www.python.org/downloads. Keep in mind that Python 3.8 is currently not compatible with popular ML packages like `tensorflow` and `pytorch`.
1. Open a terminal (bash, etc.) and run the bellow commands:
```bash
# Navigate to the directory containing the unpacked bot-tutorial content
cd bot-tutorial-master

# Create and activate virtual environment to not pollute your system or user site-packages directory
# Details about the 'venv' package can be found at https://docs.python.org/3/library/venv.html
python3 -m venv venv
source venv/bin/activate

# Install the local bot-sdk package in Edit mode so that changes to any SDK code 
# will take effect w/o re-installing. This also installs bot-sdk\requirements.txt
pip install -e bot-sdk

# Install jupyterlab, couple of  packages to help with visualization inside the notebooks,
# and some of the popular ML libraries used in the sample code
pip install jupyterlab -r requirements.txt -r requirements-ml.txt 
jupyter labextension install @pyviz/jupyterlab_pyviz @jupyter-widgets/jupyterlab-manager

# Start the server and a browser window will automatically open and you'll be navigated to
# the JupyterLab web page. Note that if you close the command prompt or Ctrl+C the process
# at any point, the notebook server and all Python kernels created to run the notebooks will be terminated.
jupyter-lab
```

Now open any of the provided tutorial notebooks and start experimenting with the bot code.

### Using Hosted JupyterHub Environment
**TODO:**

## FAQ and Troubleshooting
[FAQs](FAQ.md) <br/>
