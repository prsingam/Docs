# Install and Configure Maven, git & Docker in Jenkins server

## Install Maven
```sh
yum install wget
#downloading apache maven to /opt
wget https://dlcdn.apache.org/maven/maven-3/3.8.5/binaries/apache-maven-3.8.5-bin.tar.gz
tar -xvzf apache-maven-3.8.5-bin.tar.gz
export M2_HOME=/opt/apache-maven-3.8.5
export M2=$M2_HOME/bin
PATH=$PATH:$M2
# To set it permanently update your .bash_profile
source ~/.bash_profile
#mvn commands will work
```

## Install git
yum install git


## Install Docker
```sh
yum install docker
systemctl start docker
systemctl enable 
or

service docker start
service docker status
chkconfig docket on
```

## Assign shell to jenkins user

```sh
vi /etc/passwd
change shell from /bin/false to /bin/bash
```

## provide permissions to jenkins user in jenkins server to access docker
```sh
  sudo groupadd docker
  sudo usermod -aG docker jenkins
  sudo chmod 777 /var/run/docker.sock
```
## jenkins user has to be added to sudoers file
vi /etc/sudoers

jenkins ALL=(ALL)       NOPASSWD: ALL
