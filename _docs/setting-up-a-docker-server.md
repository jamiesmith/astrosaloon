---
title: Setting up a Docker server on Ubuntu
permalink: /docs/docker-on-ubuntu/
---

These are the steps that I used to install Docker on an Ubuntu server.  I installed
on 16.04, but the steps should be fairly portable.  The prerequisite is that you have
installed the OS, in at least the default install method, and selected that you also 
want it to be an ssh server.  Along the way we will also be setting up passwordless ssh
to the box.  Feel free to skip that step.  

In this setup I have two machines: the machine that I installed ubuntu on (referred to as ubu), 
and my MacBook (referred to as my laptop).

## Passwordless SSH

To set up passwordless ssh (so you can ssh in without a password) you first need a key
set up on the box, so we will generate a key:


```sh
# generate an SSH Key on the ubuntu box
ssh-keygen -t rsa -b 4096
```

We then need to tell the Ubuntu box that our host and key are valid.  We can do this from 
the "client" machine (probably from each machine that you want to connect from).  
I use a script for this, called `ssh-install-key`:

```console
#!/bin/sh

# Added that the mode needs to be 600 for the auth-key file
#
cat ~/.ssh/id_rsa.pub | ssh -o UserKnownHostsFile=/dev/null -o StrictHostKeyChecking=no ${*} "cat - >> ~/.ssh/authorized_keys; chmod 600 ~/.ssh/authorized_keys"
```

I need to run that script on my laptop, and tell it which machine I am pushing my key to:

```sh
ssh-install-key ubu
```

I will get prompted for my password, but it should just return.  I can now run

```sh
ssh ubu
```

and be greeted with the linux prompt.


## Update & Upgrade

Now we want to make sure that we are up-to-date, and reboot for good measure.

```sh
sudo apt update && sudo apt -y upgrade
sudo reboot
```

## Install other packages

There are several packages that I use all of the time, so I install them here.  Feel free to skip the ones that you don't need.

```sh
sudo apt install -y emacs \
    silversearcher-ag  \
    bash-completion  \
    git  \
    python  \
    python3  \
    jq  \
    iputils-ping  \
    dnsutils  \
    python-pip  \
    ksh  \
    docker
```

## Enable Password-less Sudo

Because my ubu sits about six feet from me and is within my firewall, I like to be able to sudo without a password.  Before you do this, **set the password for root!**

```sh
sudo passwd
```

Which will prompt you for YOUR password (to run sudo), and then the desired root password twice.  Now we can set it up.


```sh
sudoedit /etc/sudoers
```

we want to change the sudo group to have the "NOPASSWD" option set

```
%sudo   ALL=(ALL:ALL) NOPASSWD: ALL
```

## Install some docker things

We can now start actually installing some things that make docker life a little easier.  You might want to tweak the versions, below - 1.21.0 was current at the time

```sh
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"

sudo apt-get update
sudo apt-get install -y docker-ce

pip install awscli --upgrade --user
pip install --upgrade pip

sudo systemctl status docker

sudo usermod -aG docker jamie
# Log out then back in

# To find the latest version of compose visit" https://github.com/docker/compose/releases

sudo curl -L https://github.com/docker/compose/releases/download/1.21.0/docker-compose-$(uname -s)-$(uname -m) -o /usr/bin/docker-compose
sudo chmod +x /usr/bin/docker-compose

# Install completions:
sudo curl -L -o /etc/bash_completion.d/docker \
     https://raw.githubusercontent.com/docker/cli/master/contrib/completion/bash/docker
     
sudo curl -L -o /etc/bash_completion.d/docker-compose \
     https://raw.githubusercontent.com/docker/compose/1.21.0/contrib/completion/bash/docker-compose

# Make sure that **I** can run docker without sudo
sudo groupadd docker

# Log out/in to pick that up
```

## Set up my environment

<div class="note">
  <h5>Optional </h5>
  <p>This part is completely optional.  
</p>
</div>

I set up and tear down machines frequently, and I like having my environment where I go, so I have it
stored in a GitHub repo.  Feel free to fork it, clone it, scarf it...

```sh
cd ~/
git clone git@github.com:jamiesmith/UnixEnv.git

cd UnixEnv
./link-env.sh

# This script doesn't overwrite real files.  There will be warnings.  
# Move the files out of the way and run it again
```

Log out, then back in to pick up the enviroment.  


`mcd` is an alias for "make a directory then cd into it"

```sh
# Install the treegrep/findgrep tools
mcd ~/bin
git clone git@github.com:jamiesmith/findgrep.git
```

This is now set up with a ready-to-go docker server.  