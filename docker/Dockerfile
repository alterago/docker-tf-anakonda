FROM tensorflow/tensorflow:latest-gpu
MAINTAINER ministratio@gmail.com
RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y $buildDeps $runtimeDeps
RUN apt-get install -y git \
    && apt-get install -y vim \
    && apt-get purge -y --auto-remove $buildDeps \
    && rm -r /var/lib/apt/lists/*
ADD https://repo.continuum.io/archive/Anaconda3-5.0.1-Linux-x86_64.sh /opt/anaconda.sh
RUN chmod +x /opt/anaconda.sh
RUN bash /opt/anaconda.sh -b -p $HOME/anaconda && export PATH="$HOME/anaconda/bin:$PATH"
RUN rm /opt/anaconda.sh
RUN pip install keras
