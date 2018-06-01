Bootstrap: yum
OSVersion: 7
MirrorURL: http://mirror.centos.org/centos-%{OSVERSION}/%{OSVERSION}/os/$basearch/
Include: yum

%help

%setup

%files

%labels
  Maintainer Michael J. Stealey
  Maintainer_Email stealey@renci.org
  Anaconda_Version 5.1.0
  Python_Version 3.6.4

%environment
  export ANACONDA_VERSION=5.1.0
  export PATH=/usr/local/anaconda/bin:$PATH

%post
  export ANACONDA_VERSION=5.1.0

  yum -y install \
    bzip2 ca-certificates \
    libglib2.0-0 libxext6 libsm6 libxrender1 \
    git mercurial subversion
  cd /usr/local
  curl -L https://repo.anaconda.com/archive/Anaconda3-${ANACONDA_VERSION}-Linux-x86_64.sh -o Anaconda3-${ANACONDA_VERSION}-Linux-x86_64.sh
  bash Anaconda3-${ANACONDA_VERSION}-Linux-x86_64.sh -b -p /usr/local/anaconda

%apprun python
  exec python "${@}"

%apprun conda
  exec conda "${@}"

%runscript
  exec "${@}"

%test

