FROM centos:6

RUN mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.bakcup \
    && curl http://mirrors.163.com/.help/CentOS6-Base-163.repo -o /etc/yum.repos.d/CentOS6-Base-163.repo \
    && yum -y update \
    && yum -y install sudo \
    && yum -y clean all \
    && localedef -i en_US -f UTF-8 en_US.UTF-8 \
    && useradd -u 1000 -ms /bin/sh bwang \
    && echo 'bwang ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers


USER bwang
WORKDIR /home/bwang
COPY .condarc /home/bwang/.condarc

RUN mkdir ~/.conda \
    && curl -O https://mirrors.tuna.tsinghua.edu.cn/anaconda/miniconda/Miniconda3-latest-Linux-x86_64.sh \
    && sh Miniconda3-latest-Linux-x86_64.sh -b \
    && rm -f Miniconda3-latest-Linux-x86_64.sh \
    && eval "$(/home/bwang/miniconda3/bin/conda shell.bash hook)" \
    && conda init \
    && conda install anaconda-client conda-build
