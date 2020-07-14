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
$ python2 deploy_docker.py start
