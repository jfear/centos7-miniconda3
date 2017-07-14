FROM centos:7

MAINTAINER Justin Fear <justin.m.fear@gmail.com>

RUN yum update -y
RUN yum install -y wget git bzip2

RUN echo 'export PATH=/opt/conda/bin:$PATH' > /etc/profile.d/conda.sh && \
    wget --quiet https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh && \
    /bin/bash /Miniconda3-latest-Linux-x86_64.sh -b -p /opt/conda && \
    rm Miniconda3-latest-Linux-x86_64.sh && \
    /opt/conda/bin/conda install --yes conda==4.3.22

ENV PATH /opt/conda/bin:$PATH

RUN conda install python=3.5
RUN conda config --add channels conda-forge && \
    conda config --add channels defaults && \
    conda config --add channels bioconda && \
    conda config --add channels jfear

CMD ["/bin/bash"]
