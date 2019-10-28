
# Run Quickstart Jupyter Notebooks with Docker

You will need to install Docker on your machine as per instructions [here](https://docs.docker.com/install/). <br/>
Once you have Docker installed, open a terminal window and follow the steps below.

## Navigate to the expanded directory from the `Tutorial.zip` file

```sh
cd bot-tutorial-master
chmod -R 757 .
```

_Note_: The chmod step above ensures the container will not encounter file permission issues when persisting any file updates


## To build the docker image run
```sh
docker build -t roar-tutorial:1.0 .
```
Note: On linux, you may need to use `sudo` before your docker commands. <br/>
The above command will take couple of minutes to completed and will produce an image of ~2.5GB in size.
   
## To run container from the built image
```
docker run  --rm -p 8888:8888 -v `pwd`:/notebooks -it roar-tutorial:1.0
```

The above command does two things:
1. It binds localhost port `8888` to the container port `8888`.  If you get error: *Bind for 0.0.0.0:8888 failed: port is already allocated*, follow the steps in [port conflict resolution](#port-conflict-resolution) section and then retry the above command.
1. It also mounts the current directory (which contains the sample notebooks in addition to other files), onto the `/notebooks` directory of the running container. This enables changes to notebooks and bot code during container execution to persist on your local file system beyond the lifecycle of the container (i.e. even after the docker container is terminated).
   
## Open your Notebooks

Browse [http://localhost:8888](http://localhost:8888) with your browser (we recommend Chrome) and use `ROAR` as the password.

You can now access the ROAR Notebooks to train and build your ROAR contest prediction models!

## Port conflict resolution
Use this section if you encounter error: *Bind for 0.0.0.0:8888 failed: port is already allocated* when executing docker run step in [To run container from the built image](#To-run-container-from-the-built-image) section above.

Try any of below steps to resolve:

- Check if you have a Docker instance of `roar-tutorial` already running:
    ```
    docker ps  
    ```
    If you see a process with `IMAGE` name `roar-tuturial*` already running, copy its `CONTAINER ID` value and run below kill command to kill the instance:
    ```
    docker kill $CONTAINER_ID
    ```
- Check if you have another server app listening on port `8888`, if so you can change the destination port for example `-p 8081:8080`.

