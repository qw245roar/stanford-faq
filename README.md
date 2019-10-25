# Welcome
If you are reading this README it means you have downloaded `bot-tutorial-master` bundle from the [ROAR Getting Started](https://stanford-roar.com/#/guide) page.  You will need to complete below prerequisite steps before you can enter your bot model in a ROAR contest using one of the provided Quickstart Jupyter Notebooks. 

## Prerequisites
### Obtain a Bot Identity Token
Before you can connect to a ROAR contest via one of the provided Quickstart Jupyter Notebooks, you will need complete below steps to register your bot in the contest you wish to enter.
1. Launch the [ROAR web application](https://stanford-roar.com) and log in. 
1. Click *View & Enter Your Bots* button to the right of the contest you wish to enter your bot in and follow the bot creation wizard <br/>
1. Make sure to save your bot identity token generated for you at step 3.  NOTE: You must complete the submit action at step 4 before you can start to use your bot identity token to connect to ROAR.

### Review Contest Description
Make sure to review the Contest Description page for the contest in which you want to enter your bot model.  You can find it by browsing the [ROAR Contests](https://stanford-roar.com/#/contests) view and clicking the *Read Description* button to the right of the contest name. For DTCC contest, please review below additional resources from the `bot-tutorial-master` bundle: 
- `protocol.md`: Covers the raw protocol for question and prediction messages in the DTCC contest  
- `DTCC-Data-Exploration.ipynb`: Provides examples applying different machine learning models to DTCC data  

## Quickstart Jupyter Notebooks
In the downloaded `bot-tutorial-master` bundle you will find below Quickstart Jupyter Notebooks which you can use to build a model and enter your bot into either of the two contests hosted on ROAR (namely Tutorial/Sine and DTCC).
- `Quickstart-Beginner.ipynb` <br/>
  This quickstart uses a last value model to predict the target for a contest in ROAR.
- `Quickstart-Intermediate.ipynb` <br/>
  This quickstart uses a linear regression model to predict the target for a contest in ROAR.
- `Quickstart-Advanced.ipynb` <br/>
  This quickstart uses a temporal convolutional network model to predict the target for a contest in ROAR.
  
### Running Locally

There are two options for running a Quickstart Jupyter Notebook locally on your machine. We recommend the docker based setup unless you have most of the dependencies already available on your machine (e.g. Python 3.7 or higher, Jupyter, PiP) 

#### [Run with Docker](docker.md) <br/>

#### [Run without Docker](basic.md) <br/>

## Deployment options
Once you've built and tested your model, we do not recommend that you run it locally as your bot will disconnect from ROAR contest in the event of your workstation going to sleep or getting shut down.  Hence, it is recommended that you deploy your bot model on a more stable server infrastructure such as the Public Cloud. Some cloud options and detailed deployment steps are provided below.

[heroku](heroku.md) <br/>
[GCP](gcp.md) <br/> 

## FAQ and Troubleshooting
[FAQs](FAQ.md) <br/>
