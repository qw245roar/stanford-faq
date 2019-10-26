
# Run Quickstart Jupyter Notebooks with Docker

You will need to install Docker on your machine as per instructions [here](https://docs.docker.com/install/)
Once you have Docker installed, open a terminal windows and follow the below steps.

## Navigate to the expanded directory from the `Tutorial.zip` file:

```sh
cd bot-tutorial-master
```


_Note_: In case you get some permission error in the next steps or need read/write access to anyone to the files in this directory -- so that updates can be persisted from the container user --, run `sudo chmod -R 757 .`


## To build the docker image run: 
```sh
docker build -t roar-tutorial:1.0 .
```
Note: On linux, you may need to use `sudo` before your docker commands.
   - The above command will take couple of minutes and build ~2.5GB.
   
## To run container from the built image: 
```
docker run  --rm -p 8888:8888 -v `pwd`:/notebooks -it roar-tutorial:1.0
```
   - Above command binds localhost port `8888` to the container port `8888`. In case you get the error: **Bind for 0.0.0.0:8888 failed: port is already allocated**, you want to make sure you don't have a Docker instance already running:
   
 ```
 docker ps
 ```
 
 And if you find an instance of `roar-tuturial` already running, copy the `CONTAINER ID`: you can kill it by using
 
 ```
 docker kill $CONTAINER_ID
 ```
 
 Or if you have other server app listening on `8888`, you can change the destination port for example `-p 8081:8080`.

   - It also mounts the current directory (which contains the sample notebooks besides other files), into the `/notebooks` directory in the running container. This allows saving any changes to the notebooks and bot code when running in the container to be persisted to the local directory even after the container is stopped or deleted.
   
## Open your Notebooks

Open a browser (we recommend Chrome) to [http://localhost:8888](http://localhost:8888) and use `ROAR` as the password.

You have now access to the ROAR Notebooks continue the journey!
