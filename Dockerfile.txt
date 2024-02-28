FROM nvidia/cuda:11.2.2-cudnn8-devel-ubuntu20.04

COPY ./requirements.txt /code/requirements.txt
WORKDIR /code

RUN apt-get update && apt-get -y upgrade
RUN apt install -y curl python3 python3-distutils
RUN curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py && python3 get-pip.py

RUN pip install -r requirements.txt