# VAF Correlation Pipeline

## Summary 
This pipeline plots VAF values for various pairs of Samples (Diagnose-Relapse/Diagnose-Diagnose/Relapse-Relapse, label genes of interest and generates plots of total number of mutation across various samples.

## Requirements
1. [Docker](https://www.docker.com/get-started)


## How to run
- Install [docker for Mac](https://hub.docker.com/editions/community/docker-ce-desktop-mac) (Check your installation by typing `docker -h` in the terminal and you should see docker help manual open)
- Open docker terminal and execute the following commands

#### Build a docker image
Save the Dockerfile in a folder (do not rename the Dockerfile file)

`docker build -t <image_repository>:<tag> <path/to/Dockerfile>`



#### Running the docker image
`docker run -i -t <image_repository>:<tag> /bin/bash`

The above command will open an interactive shell, where you will find the resulting files and folders generated by the pipeline. You can navigate through the folders using standard linux commands. 


#### Coping files from Docker container to Host
`docker cp <container_Id>:/file/path/within/container /host/path/target`


# RNA VAF Comparisons

## Summary
This script calculates variant allele frequencies for all non-silent VEP passed RNA variants and annotates with its DNA counterpart. The resulting file is a DNA MAF with RNA variants and its corresponding variant allele frequencies.

## Requirements
1. DNA MAF
2. RNA MAF (RNA variants)
3. Clinical file

## How to run
`Rscript DNA-RNA-VAF.R <DNA_MAF.rda> <RNA_MAF.maf> <clinical_file.txt>`
