FROM centos:6

RUN mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.bakcup \
    && curl http://mirrors.163.com/.help/CentOS6-Base-163.repo -o /etc/yum.repos.d/CentOS6-Base-163.repo \
    && yum -y update \
    && yum -y groupinstall 'Development Tools' \
    && yum -y install http://opensource.wandisco.com/centos/6/git/x86_64/wandisco-git-release-6-1.noarch.rpm \
    && yum -y install git \
    && yum -y clean all \
    && localedef -i en_US -f UTF-8 en_US.UTF-8
