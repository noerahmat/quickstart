# ADD USER kube-prod


```sh
sudo useradd -s /bin/bash -d /home/kube-prod/ -m -G sudo kube-prod
sudo passwd kube-prod
```


```sh
sudo mkdir /home/kube-prod/.ssh/
sudo chmod 0700 /home/kube-prod/.ssh/
sudo -- sh -c "echo 'ssh-rsa XXXX-public-ssh-XXXX kube-prod' > /home/kube-prod/.ssh/authorized_keys"
sudo chown -R kube-prod:kube-prod /home/kube-prod/.ssh/
```

**  https://www.cyberciti.biz/faq/create-a-user-account-on-ubuntu-linux/
**  https://www.cyberciti.biz/faq/ubuntu-18-04-setup-ssh-public-key-authentication/

#Now you can log in with ssh keys:
```sh
$ ssh -i key.pem kube-prod@your-aws-server-ip-here
```


####INSTALL DOCKER#####
```sh
curl -fsSL https://get.docker.com -o get-docker.sh
sh get-docker.sh
```

#cek
#docker --version

#install docker compose

```sh
sudo apt  install docker-compose -y
```
#cek
#docker-compose --version


#install docker machine

```sh
base=https://github.com/docker/machine/releases/download/v0.16.0 &&
  curl -L $base/docker-machine-$(uname -s)-$(uname -m) >/tmp/docker-machine &&
  sudo install /tmp/docker-machine /usr/local/bin/docker-machine
```

#cek
#docker-machine --version


#sudo user docker
#sudo groupadd docker

```sh
sudo usermod -aG docker $USER
```

### !!!!!
sudo reboot

```sh
docker login
```

# !!cannot-login-to-docker-account

```sh
sudo apt install gnupg2 pass
```

#set access
```sh
sudo chown "$USER":"$USER" /home/"$USER"/.docker -R
sudo chmod g+rwx "$HOME/.docker" -R
```

