# createrepo
Notes to create a local yum repo from a remote on an Ubuntu server
Just some notes to self for creating a local yum repo n an Ubuntu box.

The expired SSL certs and seemingly unstructured state of the Jenkins or Jenkins-ci repos prompted me in this endeavor.

# Steps to perform on the Ubuntu box
1) sudo aptitude install yum-utils
2) sudo aptitude install createrepo
3) sudo vi /etc/yum.conf
 

[main]
cachedir=/var/cache/yum
debuglevel=2
logfile=/var/log/yum.log

4) sudo mkdir -p /var/cache/yum
5) sudo mkdir -p /path/to/where/you/want/to/save/the/below
6) cd /path/to/where/you/want/to/save/the/below
7) wget --no-check-certificate -rkpN -e robots=off  https://mirrors.jenkins.io/redhat/
8) cd mirrors.jenkins.io/redhat
9) createrepo -v -p .

10) tree
.
* | ├── mirrors.jenkins.io
* | └── redhat
* | ├── jenkins-2.180-1.1.noarch.rpm
* | ├── jenkins-2.181-1.1.noarch.rpm
* | ├── jenkins-2.182-1.1.noarch.rpm
* | ├── jenkins-2.183-1.1.noarch.rpm
* | ├── jenkins-2.184-1.1.noarch.rpm
* | ├── jenkins-2.185-1.1.noarch.rpm
* | ├── jenkins-2.186-1.1.noarch.rpm
* | ├── jenkins-2.187-1.1.noarch.rpm
* | ├── jenkins-2.189-1.1.noarch.rpm
* | ├── jenkins-2.190-1.1.noarch.rpm
* | ├── jenkins-2.191-1.1.noarch.rpm
* |  ├── repodata
* |       ├── 134f22b5ee1052b311ac47f5d9156ce960a87cc2ba437bae88f213084a92e86d-primary.sqlite.bz2
* |       ├── 15a095717d51930038e4c0193befbed7f647a010a28340dd9da62db6dc24a174-filelists.sqlite.bz2
* |       ├── 2e903383cdbbbd2ef49b62307919aa4d805cb1c76d162662ee499fca4b6071b5-other.sqlite.bz2
* |       ├── 3853ebb42398c4e25d82630aa3f8e9348dab2c8de9da69426bd38e01f7a054f6-filelists.xml.gz
* |       ├── 83a25d1200c3c16dc37c8e6bb4de435b98de9fa7c6716d0a4a303fdf9fd62e6d-other.xml.gz
* |       ├── c424315a92f64aa546652e887450355b81ec0587a93feee6093912ec8b32aefb-primary.xml.gz
* |       └── repomd.xml
2 directories, 18 files
