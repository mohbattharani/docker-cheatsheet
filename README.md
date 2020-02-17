#### Docker-cheatsheet
 Build a Docker image
```docker build -t [image_name]:[tag] .```

 Run a Docker container specifying a name
```docker run --name [container_name] [image_name]:[tag]```

 Fetch the logs of a container
```docker logs -f [container_id_or_name]```

 Run a command in a running container
``` docker exec -it [container_id_or_name] bash```

 Show running containers
``` docker ps```

 Show all containers
``` docker ps -a```

 Show Docker images
```docker images```

 Stop a Docker container
``` docker stop [container_id_or_name]```

 Remove a Docker container
```docker rm [container_id_or_name]```

 Remove a Docker image
``` docker rmi [image_id_or_name]```

```docker file/location/in/base/os container-id:/file-location </br>```
 
 Remove untagged Docker images
``` docker image prune -fa ```


Docker tensorflow run
Need nvidia-docker installed to run gpu on containers <br/>
Nvidia-docker: https://github.com/NVIDIA/nvidia-docker/wiki/Installation-(version-2.0) <br/>

``` docker run --runtime=nvidia -it --rm tensorflow/tensorflow:devel-gpu-py3 bash <br/>```

#### Jupyter notebook with Docker
install notebook on docker image as:
```pip install notebook```

Run follwing command to run docker image
``` docker run -it --rm -p 8080:8080 image </br>```

Following command start notebook 
``` jupyter notebook --ip 0.0.0.0 --no-browser --allow-root </br>```

Install graphviz on Docker to render images in notebook.

```pip install graphviz```

Run ([ref](https://github.com/pangeo-data/helm-chart/pull/45/commits/60e397299133c2915f5b08fcf36a146eb09c730f))

```
apt-get update \
  && apt-get install -yq --no-install-recommends libfuse-dev nano fuse vim git \
  && apt-get install -yq --no-install-recommends libfuse-dev nano fuse vim git graphviz \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*
USER $NB_USER 
```
