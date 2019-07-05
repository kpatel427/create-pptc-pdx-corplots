FROM ubuntu:18.04
FROM python:3.6
FROM r-base

CMD source ~/.bashrc

MAINTAINER Khushbu Patel <patelk26@email.chop.edu>
  
  # installing Git
  RUN apt-get update && apt-get install -y git

# clone the most recent version of the pipeline
WORKDIR /home/user/
  RUN git clone https://github.com/kpatel427/create-pptc-pdx-corplots.git


# Install all the software needed to run the pipeline
#RUN apt-get install -qqy python3-setuptools python3-docutils python3-flask python3.6 python-pip
RUN apt-get install -qqy python3.6 python-pip
RUN pip install --upgrade pip && \
pip install --no-cache-dir pandas


# Setting working directory
WORKDIR /home/user/VAF-corr-docker


# Executing scripts
RUN [ "/usr/bin/bash", "/home/user/VAF-corr-docker/pipeline.sh" ]




# FROM ubuntu:18.04
# FROM python:3.7
# FROM r-base
# 
# CMD source ~/.bashrc
# 
# MAINTAINER Khushbu Patel <patelk26@email.chop.edu>
#   
#   # installing Git
#   RUN apt-get update && apt-get install -y git
# 
# # clone the most recent version of the pipeline
# WORKDIR /home/user/
#   RUN git clone https://github.com/marislab/create-pptc-pdx-corplots.git
# 
# 
# # Install all the software needed to run the pipeline
# RUN apt-get -y upgrade
# RUN apt install -y python3-pip python3.7
# #RUN pip3 install -r requirements.txt
# #ONBUILD COPY requirements.txt /home/user/
# #ONBUILD RUN pip install --no-cache-dir -r requirements.txt
# #RUN pip3 install -r requirements.txt
# ARG PANDAS_VERSION=0.23.0
# RUN pip3 install pandas==${PANDAS_VERSION}
# 
# 
# # Setting working directory
# WORKDIR /home/user/create-pptc-pdx-corplots/VAF-corr-plots-docker
# 
# 
# # Executing scripts
# RUN [ "/usr/bin/bash", "/home/user/create-pptc-pdx-corplots/VAF-corr-plots-docker/pipeline.sh" ]
# #ENTRYPOINT /home/user/create-pptc-pdx-corplots/VAF-corr-plots-docker/pipeline.sh
