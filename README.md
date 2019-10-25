# FAQ and Troubleshooting for ROAR Stanford

## Getting started: running ROAR notebooks locally

#### Docker Install
You will need to install Docker on your machine as per instructions [here](https://docs.docker.com/install/)
Once you have Docker installed, open a terminal windows and follow the below steps.


##### Build and Run Docker Container
1. Navigate to the expanded directory from the Tutorial.zip file: `cd bot-tutorial-master` 
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
   
1. Open a browser (we recommend Chrome) to http://localhost:8888
1. Launch the Welcome notebook to continue the journey!


## Deployment options

[heroku](heroku.md)
