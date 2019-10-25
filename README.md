# Welcome
If you are reading this README it means you have downloaded Tutorial.zip (bot-tutorial-master) from the [ROAR Getting Started](stanford-roar.com/#/guide) page.  You will need to complete below prerequisite steps before you can enter your bot model in a ROAR contest using one of the provided Quickstart Jupyter Notebooks. 

# Prerequisites
## Obtain a Bot Identity Token
Before you can connect to a ROAR contest via the Jupyter Notebook Quickstart, you will need to register your bot in the respective contest and obtain the bot identity token. You will then use this token which you will use to connect your Jupyter Notebooks to ROAR for the respective contest.
To obtain a bot identity, launch ROAR web application by browsing https://stanford-roar.com and logging in.   
Then, for each listed contest (i.e. Tutorial and DTCC): <br/>
1. Click *Enter Bot* button to the right of the contest name and follow the bot creation wizard <br/>
1. Make sure to save your bot identity token generated for you at step 3.  

## Review Contest Description
Make sure to review the Contest Description page for the contest in which you want to enter your bot model.  You can find it by browsing the [ROAR Contests](stanford-roar.com/#/contests) view and clicking the *View & Enter Your Bots* button to the right of the contest name. For DTCC contest, also make sure to review the protocol.md document included in the bot-tutorial-master download which covers the raw protocol for question and prediction messages in the DTCC contest.  

## Getting started: running ROAR notebooks locally

#### Docker Install
You will need to install Docker on your machine as per instructions [here](https://docs.docker.com/install/)
Once you have Docker installed, open a terminal windows and follow the below steps.


##### Build and Run Docker Container
1. Navigate to the expanded directory from the `Tutorial.zip` file:

```sh
cd bot-tutorial-master
```

Note: In case you get some permission error or need read/write access to anyone to the files in this directory -- so that updates can be persisted from the container user--, run `sudo chmod -R 757 .`

1. To build the docker image run: 
```sh
docker build -t roar-tutorial:1.0 .
```
Note: On linux, you may need to use `sudo` before your docker commands.
   - The above command will take couple of minutes and build ~2.5GB.
   
1. To run container from the built image: 
```
docker run -p 8888:8888 -v `pwd`:/notebooks -it roar-tutorial:1.0
```
   - Above command binds local host port `8888` to the container port `8888`. In case you have other server app listening on `8888` you'd want to change the first port of the `-p` argument.

   - It also mounts the current directory (which contains the sample notebooks besides other files), into the `/notebooks` directory in the running container. This allows saving any changes to the notebooks and bot code when running in the container to be persisted to the local directory even after the container is stopped or deleted.
   
1. Open a browser (we recommend Chrome) to [http://localhost:8888](http://localhost:8888) and use ROAR as the password.

1. Launch the Welcome notebook to continue the journey!


## Deployment options

[heroku](heroku.md) <br/>
[GCP](gcp.md)

# FAQ and Troubleshooting
[FAQs](FAQ.md) <br/>
