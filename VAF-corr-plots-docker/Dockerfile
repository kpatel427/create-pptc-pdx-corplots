FROM ubuntu:18.04
FROM python:3.7
FROM r-base

CMD source ~/.bashrc

MAINTAINER Khushbu Patel <patelk26@email.chop.edu>
  
# installing Git
RUN apt-get update && apt-get install -y git

# clone the most recent version of the pipeline
WORKDIR /home/user/
RUN git clone https://github.com/kpatel427/create-pptc-pdx-corplots.git

RUN apt-get install -qqy python-pip
RUN pip install --upgrade pip && \
pip install --no-cache-dir pandas

WORKDIR /home/user/create-pptc-pdx-corplots/VAF-corr-plots-docker/

RUN [ "/bin/sh", "/home/user/create-pptc-pdx-corplots/VAF-corr-plots-docker/pipeline.sh" ]
