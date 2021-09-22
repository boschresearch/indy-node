# Container containing all dependencies required for executing unit test on 'indy-node' Python module.
# Based upon / inspired by work of the indy-node docker working group of the ID Union project.
# see https://github.com/IDunion/indy-node-container/blob/main/build/Dockerfile.ubuntu18
#
# Intended use: docker run --mount src=[local path of indy-node repo],target=/home/indy/indy-node,type=bind [IMAGE] ./exec_tests.sh [ARGS]

FROM hyperledger/indy-core-baseci:0.0.3-master

# Install environment
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys CE7709D068DB5E88 \
    && apt-get update -y && apt-get upgrade -y && apt-get install -y \
    git \
    wget \
    python3-nacl \
    libindy-crypto=0.4.5 \
    libindy=1.15.0~1625-xenial \
# rocksdb python wrapper
    libbz2-dev \
    zlib1g-dev \
    liblz4-dev \
    libsnappy-dev \
    rocksdb=5.8.8 \
    ursa=0.3.2-2 \
# Build dependencies
    gcc \
    make

RUN update-alternatives --install /usr/bin/python python /usr/bin/python3 1

# RUN add-apt-repository ppa:deadsnakes/ppa
# RUN apt-get update
# RUN apt-get install python3.5-dev
# RUN pip3 install -U \
#     'pip<10.0.0'


RUN pip install python3-indy==1.15.0-dev-1625 indy-plenum==1.13.0.dev1034

# Install dev helper 
RUN pip install flake8 autopep8


ADD indy_config.py /etc/indy/

