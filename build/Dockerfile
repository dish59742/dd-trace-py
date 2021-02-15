FROM ubuntu:20.04
RUN apt-get update && apt-get install -y automake cmake git libtool make build-essential software-properties-common \
    && add-apt-repository ppa:deadsnakes/ppa \
    && apt-get install -y python3 python3-pip python3-dev \
    && git clone --recursive https://github.com/DataDog/dd-trace-py.git \
    && cd dd-trace-py \
    && which python3 \
    && python3 -m pip install -U setuptools wheel \
    && python3 --version

RUN echo $CC

RUN cd dd-trace-py && python3 -m pip install cython && python3 setup.py bdist_wheel && ls dist

RUN uname -m
