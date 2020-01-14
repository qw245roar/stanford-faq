# Welcome
If you are reading this README it means you have downloaded `bot-tutorial-master` bundle from the [ROAR Getting Started](https://web.stanford-roar.com/#/guide) page.  You will need to complete below prerequisite steps before you can enter your bot model in a ROAR contest using one of the provided Jupyter Notebooks in this bundle. 

## Prerequisites

### Obtain a Bot Identity Token
Before you can connect to a ROAR contest via one of the provided Quickstart Jupyter Notebooks, you will need complete below steps to register your bot in the contest you wish to enter.
1. Launch the [ROAR web application](https://stanford-roar.com) and log in. 
1. Click *View & Enter Your Bots* button to the right of the contest you wish to enter your bot in and follow the bot creation wizard.
1. Use *COPY TOKEN* button to put the identity token generated for your bot in the Clipboard. You'll need to paste this token in the Jupyter notebooks described later in order for your bot code to be able to connect to the ROAR server.

### Obtain an IEX free-tier token
The Roar notebook below (DTCC-Quickstart.ipynb) requires an API token from the IEX provider.  The steps for doing so are as follows:
1. Go to www.iexcloud.io
2. Click "Get Started" in the upper right.
3. Fill out and submit the form.
4. Click "Select Free Plan" in the lower left.
5. An email will be sent to you to verify your email address.  Go to that email and click the link it gives.
6. This will bring up a screen prompting you to enter a code.  Go to your email and find that code in a second email that was sent.  Enter the code.
7. You should now be able to log in.  Do so, and navigate to "API tokens" in the upper left.
8. Copy your API token.  This is the one to be used as the IEX token (not the ROAR token) in the notebook below.

## Review Contest Description
Make sure to review the Contest Description page for the contest in which you want to enter your bot model.  You can find it by browsing the [ROAR Contests](https://web.stanford-roar.com/#/contests) view and clicking the *Read Description* button to the right of the contest name.

## Quickstart Jupyter Notebook
In the downloaded `bot-tutorial-master` bundle you will find two Jupyter Notebooks which you can use to first explore the DTCC data, and then create your bot.
### `DTCC-Quickstart.ipynb`
  This quickstart allows you to create a bot.  In it, you will first download the history for the DTCC data.  From there, you can create your model and then deploy it.  A real example using a Temporal Convolutional Network (TCN) is in place.  Do not feel that you need to use this model; it is there as an example only.
### `DTCC-Data-Exploration.ipynb`
  This notebook allows you to some some exploratory analysis of some historical DTCC data.  It is meant to help you better understand the dataset and its quirks/intricacies.
  
### Running Notebooks and Bots Locally
**Caution**: A locally-deployed model will only run when your computer is awake and has internet connection. For a bot to participate in the online contest for extended period of time see the JupyterHub section below.

The steps in this section describe how to set-up Python and JupyterLab environment on
your local workstation or laptop. The instructions are specific for Mac and Linux OS, 
but with small tweaks can be made to work for Windows.

1. **NodeJS** LTS version (e.g. 8, 10, 12) is required by Jupyter and can be installed from  https://nodejs.dev/how-to-install-nodejs

1. **Python 3.7** is required and install can be installed from https://www.python.org/downloads. Keep in mind that Python 3.8 is currently not compatible with popular ML packages like `tensorflow` and `pytorch`.

1. Open a terminal (bash, etc.) and run the bellow commands:

```sh
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
./venv/bin/jupyter-lab
```

Now open any of the provided tutorial notebooks and start experimenting with the bot code.

### Using ROAR Hosted Jupyter Environment

Jupyter Notebooks are available at https://jupyter.stanford-roar.com. Every participant has allocated `10 gigabytes`
space in their `HOME` directory to host code, data and models. Your `HOME` directory is the notebook root directory in JupyterLab.

ROAR Bot SDK and tutorial notebooks are available at `/roar` read-only location of the JupyterHub session. To get a copy of Quickstart Notebooks and samplem model code that you can modify, simply copy them to your home directory by opening a Terminal windows from the Jupyter Launcher and run: 

```
cp /roar/*.ipynb .
cp -r /roar/models .
```

#### Adding python packages

In a Notebook, launch for example:

```python
!conda install -y tensorflow
```

#### Restarting my Notebook server

In some cases the version of the ROAR SDK will be updated by the JupyterHub admins. If you need to pick such updated version,
simply restart your notebook session. Any saved files in your `HOME` directory will be still available in the new session. The steps are:
* Go to "File" menu -> "Hub Control Server".
* Click "Stop my service" **two** times.
* Click "Start My Server" and in few seconds your new session will be ready.

## FAQ and Troubleshooting
[FAQs](FAQ.md)
