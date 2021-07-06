# crossMoDA Challenge - MICCAI 2021
Example docker container for the crossMoDA Segmentation Challenge. The script simply threshold the hrT2 images to predict the VS and cochlea.

## Build the Docker image
`Dockerfile` contains all the information used to create your Docker container. 
In our case, it uses the `continuumio/miniconda` image and install additionnal Python libraries. Then, it automatically execute a dummy algorithm `src/run_infenrece.py` on all the scans.

To build the docker image:

```
docker build -f Dockerfile -t [your image]
```

## Docker commands
Containers submitted to the challenge will be run with the following commands:
```
docker run --rm -v [input directory]:/input/:ro -v [output directory]:/output -it [your image]
```
## Credits
This repository is based on the intructions provided for the MICCAI WMH segmentation challenge 2017. 