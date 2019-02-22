FROM pytorch/pytorch:1.0.1-cuda10.0-cudnn7-devel

# Install Python & dependencies
RUN \
  apt-get update && \
  apt-get install -y bzip2 curl build-essential curl git && \
  curl -sSL https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh -o /tmp/miniconda.sh && \
  bash /tmp/miniconda.sh -bfp /usr/local && \
  rm -rf /tmp/miniconda.sh

RUN conda install python=3.6

RUN git clone https://github.com/nvidia/apex && \
    cd apex && \
    python setup.py install --cuda_ext --cpp_ext && \
    rm -rf /apex

CMD "/bin/bash"