from ubuntu:16.04

RUN apt-get update
RUN apt-get install build-essential software-properties-common -y
RUN apt-get install libssl-dev -y

# add ppa for toolchain
RUN add-apt-repository ppa:ubuntu-toolchain-r/test -y
RUN apt-get update

# install gcc 6
RUN apt-get install gcc-6 g++-6 -y
RUN update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-6 60 --slave /usr/bin/g++ g++ /usr/bin/g++-6

# install pip3
RUN apt-get install python3-pip -y

# install p4python
RUN pip3 install p4python

ENTRYPOINT ["/usr/bin/tail", "-f", "/dev/null"]
