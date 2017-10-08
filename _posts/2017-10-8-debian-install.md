---
layout: post
title: "Debian System Install"
date: 2017-10-08 10:00 +0800
author: lijiarui
---

using 马克飞象 cannot work as expect. It looks strange on evernote. After a while I will forget the basic install command, so put it here.

<!--more-->

# 1.view system info
```
uname -a
hostname NEW_NAME // change hostname
```

# 2.change default port
```
vi /etc/ssh/sshd_config
```
Edit the line which states 'Port 22'. But before doing so, you'll want to read the note below. Choose an appropriate port, also making sure it not currently used on the system.
```
# What ports, IPs and protocols we listen for
Port 50683
```
restart
```
/etc/init.d/ssh restart
```

# 3. install sudo
sudo is not installed on Debian by default. Make sure your system is up-to-date and install it.
In Debian 8 (Jessie) add-apt-repository command utility is available under software-properties-common package. So use following command to install it
```
aptitude install sudo
sudo apt-get install software-properties-common
```

# 4.install node7
```
curl https://raw.githubusercontent.com/creationix/nvm/v0.11.1/install.sh | bash

nvm install 7
nvm alias default 7
```

# 5.install git
```
sudo apt-get update
sudo apt-get install git-core
```

# 6.install typescript
```
npm install -g ts-node
npm install -g typescript
```

# 7.install docker
[Reference Link](https://docs.docker.com/engine/installation/linux/debian/#install-using-the-repository)
```
sudo apt-get install \
     apt-transport-https \
     ca-certificates \
     curl \
     python-software-properties

curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -

sudo apt-get install software-properties-common

sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/debian \
   $(lsb_release -cs) \
   stable"

sudo apt-get update
sudo apt-get install docker-ce
apt-cache madison docker-ce
sudo docker run hello-world
```

# 8.install mongodb
[Reference Link](https://www.digitalocean.com/community/tutorials/how-to-install-mongodb-on-debian-8)
```
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 0C49F3730359A14518585931BC711F9BA15703C6

echo "deb http://repo.mongodb.org/apt/debian jessie/mongodb-org/3.4 main" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.4.list

sudo apt-get update
sudo apt-get install -y mongodb-org
sudo systemctl enable mongod.service
sudo systemctl start mongod
```

# 9.add cnpm Permanently
[Reference Link](https://github.com/Chatie/wechaty/wiki/NPM)
```
npm config set registry https://registry.npm.taobao.org
```

# 10. wechaty
```
npm install

docker run -t -i --rm --privileged --net=host --volume="$(pwd)":/bot --name=juxiaomi zixia/wechaty:latest src/index.ts
```

# 11. change alias
```
vi .zshrc
vi .bashrc
```


# 12. install tree
```
apt-get update && apt-get install tree
aptitude update && aptitude install tree
``` 
