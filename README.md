# Installing Digital Slide Archive
```
$ sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
$ sudo apt-get update
$ sudo apt-get install docker-ce
$ sudo apt-get install python-pip
$ sudo apt-get install build-essential libssl-dev libffi-dev python-dev
$ python2 -m pip install docker-py ansible --user
$ sudo groupadd docker
$ sudo gpasswd -a $USER docker
$ newgrp docker
$ sudo apt-get install openssh-server
$ sudo apt-get install ssh
$ sudo nano /etc/ssh/sshd_config # check port
$ ssh cwlab913@localhost -p 518
$ git clone https://github.com/DigitalSlideArchive/digital_slide_archive.git
$ cd digital_slide_archive/ansible
```
# Choose Another Directory for Mongo
```
$ mkdir /media/cwlab913/55cd4b0f-9a55-4122-86c5-a0d0f3ac95f81/MongoLocal
$ sudo chown cwlab913 /media/cwlab913/55cd4b0f-9a55-4122-86c5-a0d0f3ac95f81/MongoLocal
$ mkdir /media/cwlab913/55cd4b0f-9a55-4122-86c5-a0d0f3ac95f81/MongoLocal/girder_db
$ sudo mkdir /media/cwlab913/55cd4b0f-9a55-4122-86c5-a0d0f3ac95f81/HistomicsData
$ sudo chmod g+s /media/cwlab913/55cd4b0f-9a55-4122-86c5-a0d0f3ac95f81/HistomicsData
$ sudo chown cwlab913 /media/cwlab913/55cd4b0f-9a55-4122-86c5-a0d0f3ac95f81/HistomicsData
$ sudo mkdir /media/cwlab913/55cd4b0f-9a55-4122-86c5-a0d0f3ac95f81/LocalAssetstore
$ sudo chown cwlab913 /media/cwlab913/55cd4b0f-9a55-4122-86c5-a0d0f3ac95f81/LocalAssetstore
$ mkdir /media/cwlab913/55cd4b0f-9a55-4122-86c5-a0d0f3ac95f81/LocalAssetstore/girderAssetStore
```
# Start Server
```
$ python2 deploy_docker.py start --db=/media/cwlab913/55cd4b0f-9a55-4122-86c5-a0d0f3ac95f81/MongoLocal/girder_db --assetstore=/media/cwlab913/55cd4b0f-9a55-4122-86c5-a0d0f3ac95f81/LocalAssetstore/girderAssetStore --logs=/media/cwlab913/55cd4b0f-9a55-4122-86c5-a0d0f3ac95f81/HistomicsData/logs
```
# Stop and Remove Server
```
$ python2 deploy_docker.py stop
$ python2 deploy_docker.py rm
```
# Accessing Image Tile Prerequisite
```
$ python2 -m pip install girder-client
```
