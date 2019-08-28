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
├── mirrors.jenkins.io
│   └── redhat
│       ├── jenkins-2.100-1.1.noarch.rpm
│       ├── jenkins-2.101-1.1.noarch.rpm
│       ├── jenkins-2.102-1.1.noarch.rpm
│       ├── jenkins-2.103-1.1.noarch.rpm
│       ├── jenkins-2.104-1.1.noarch.rpm
│       ├── jenkins-2.105-1.1.noarch.rpm
│       ├── jenkins-2.106-1.1.noarch.rpm
│       ├── jenkins-2.107-1.1.noarch.rpm
│       ├── jenkins-2.108-1.1.noarch.rpm
│       ├── jenkins-2.109-1.1.noarch.rpm
│       ├── jenkins-2.110-1.1.noarch.rpm
│       ├── jenkins-2.111-1.1.noarch.rpm
│       ├── jenkins-2.112-1.1.noarch.rpm
│       ├── jenkins-2.113-1.1.noarch.rpm
│       ├── jenkins-2.114-1.1.noarch.rpm
│       ├── jenkins-2.115-1.1.noarch.rpm
│       ├── jenkins-2.116-1.1.noarch.rpm
│       ├── jenkins-2.117-1.1.noarch.rpm
│       ├── jenkins-2.118-1.1.noarch.rpm
│       ├── jenkins-2.119-1.1.noarch.rpm
│       ├── jenkins-2.120-1.1.noarch.rpm
│       ├── jenkins-2.121-1.1.noarch.rpm
│       ├── jenkins-2.122-1.1.noarch.rpm
│       ├── jenkins-2.124-1.1.noarch.rpm
│       ├── jenkins-2.125-1.1.noarch.rpm
│       ├── jenkins-2.126-1.1.noarch.rpm
│       ├── jenkins-2.127-1.1.noarch.rpm
│       ├── jenkins-2.128-1.1.noarch.rpm
│       ├── jenkins-2.129-1.1.noarch.rpm
│       ├── jenkins-2.130-1.1.noarch.rpm
│       ├── jenkins-2.131-1.1.noarch.rpm
│       ├── jenkins-2.132-1.1.noarch.rpm
│       ├── jenkins-2.133-1.1.noarch.rpm
│       ├── jenkins-2.134-1.1.noarch.rpm
│       ├── jenkins-2.135-1.1.noarch.rpm
│       ├── jenkins-2.136-1.1.noarch.rpm
│       ├── jenkins-2.137-1.1.noarch.rpm
│       ├── jenkins-2.138-1.1.noarch.rpm
│       ├── jenkins-2.140-1.1.noarch.rpm
│       ├── jenkins-2.141-1.1.noarch.rpm
│       ├── jenkins-2.142-1.1.noarch.rpm
│       ├── jenkins-2.143-1.1.noarch.rpm
│       ├── jenkins-2.144-1.1.noarch.rpm
│       ├── jenkins-2.145-1.1.noarch.rpm
│       ├── jenkins-2.146-1.1.noarch.rpm
│       ├── jenkins-2.147-1.1.noarch.rpm
│       ├── jenkins-2.148-1.1.noarch.rpm
│       ├── jenkins-2.149-1.1.noarch.rpm
│       ├── jenkins-2.150-1.1.noarch.rpm
│       ├── jenkins-2.151-1.1.noarch.rpm
│       ├── jenkins-2.152-1.1.noarch.rpm
│       ├── jenkins-2.153-1.1.noarch.rpm
│       ├── jenkins-2.154-1.1.noarch.rpm
│       ├── jenkins-2.155-1.1.noarch.rpm
│       ├── jenkins-2.156-1.1.noarch.rpm
│       ├── jenkins-2.157-1.1.noarch.rpm
│       ├── jenkins-2.158-1.1.noarch.rpm
│       ├── jenkins-2.159-1.1.noarch.rpm
│       ├── jenkins-2.160-1.1.noarch.rpm
│       ├── jenkins-2.161-1.1.noarch.rpm
│       ├── jenkins-2.162-1.1.noarch.rpm
│       ├── jenkins-2.163-1.1.noarch.rpm
│       ├── jenkins-2.164-1.1.noarch.rpm
│       ├── jenkins-2.165-1.1.noarch.rpm
│       ├── jenkins-2.166-1.1.noarch.rpm
│       ├── jenkins-2.167-1.1.noarch.rpm
│       ├── jenkins-2.168-1.1.noarch.rpm
│       ├── jenkins-2.169-1.1.noarch.rpm
│       ├── jenkins-2.170-1.1.noarch.rpm
│       ├── jenkins-2.171-1.1.noarch.rpm
│       ├── jenkins-2.172-1.1.noarch.rpm
│       ├── jenkins-2.173-1.1.noarch.rpm
│       ├── jenkins-2.174-1.1.noarch.rpm
│       ├── jenkins-2.175-1.1.noarch.rpm
│       ├── jenkins-2.176-1.1.noarch.rpm
│       ├── jenkins-2.177-1.1.noarch.rpm
│       ├── jenkins-2.178-1.1.noarch.rpm
│       ├── jenkins-2.179-1.1.noarch.rpm
│       ├── jenkins-2.180-1.1.noarch.rpm
│       ├── jenkins-2.181-1.1.noarch.rpm
│       ├── jenkins-2.182-1.1.noarch.rpm
│       ├── jenkins-2.183-1.1.noarch.rpm
│       ├── jenkins-2.184-1.1.noarch.rpm
│       ├── jenkins-2.185-1.1.noarch.rpm
│       ├── jenkins-2.186-1.1.noarch.rpm
│       ├── jenkins-2.187-1.1.noarch.rpm
│       ├── jenkins-2.189-1.1.noarch.rpm
│       ├── jenkins-2.190-1.1.noarch.rpm
│       ├── jenkins-2.191-1.1.noarch.rpm
│       └── repodata
│           ├── 128e0e346a712258225d095fb497e93e5c008bb66bfa04267d012c82a8f450c0-primary.xml.gz
│           ├── 3680fe57b7b97a16db07f44076acc13a4037b28aa8aaa791ee12d1d1a91ea3d0-filelists.xml.gz
│           ├── 5d2fc6292e18670766683e01bc27849f87c6222ac24257f80d5de57cd27fd573-primary.sqlite.bz2
│           ├── 7f13915818eded3ebcc7f8e8bb6bc03ff384e85319d553740f8c0f45ff31c182-filelists.sqlite.bz2
│           ├── 9bfc2ec7dac9819a687d56d39fcc07b7f54a99a733bb05add7dc451514e14e94-other.sqlite.bz2
│           ├── f5baf1e33952f7afc36517ff32211070f48126b2492ab281ec58ddb93c0a2a14-other.xml.gz
│           └── repomd.xml
└── rsync.jenkins

3 directories, 97 files
