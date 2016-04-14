---
layout: post
title: Developing Smart Contracts in Ethereum with Dapple and Visual Studio Code in Windows with Docker.
date: '2016-04-14 04:49:04'
---

Dapple from its origins as Python tool to its current implementation in node.js has fascinated me. With dapple you can unit test your Ethereum Solidty contracts using Solidity, the same way as if you test C# code with C# Code, Javascript, etc.

But dapple is not just limited to testing, it allows you to, install, package and deploy and bundle scripts.

For more information about dapple check [the dapple Github repository](https://github.com/nexusdev/dapple)

Installing Dapple in Windows, has been always an issue, similar to Ethereum, there are lots of hurdles to get through due to the different dependencies.

Microsoft has announced recently the Windows 10 Ubuntu Bash Shell which will eventually solve this issues, but at the moment the current preview release is in early stages.

###Docker and Nexus to the rescue

The Nexus team responsible for Dapple (well Ryan) has a docker image which includes all the Ethereum related tools already installed.

It includes :

* NodeJS
* Python + pip
* solc
* IPFS
* geth
* Git
* Vim
* inotifytools
* All of Nexus' Github repositories
* An FTP server
* A unprivileged default user

You can find it here: https://hub.docker.com/r/ryepdx/nexus_dev/

But to simplify things, I have created another version which includes Dapple already installed from source. (npm install -g or link can take a long time).

You can find it here: https://hub.docker.com/r/juanfranblanco/dapple/

###Adding Visual Studio Code to the mix

Coding using Vim inside Docker can be a dunting experience if you are not used to Vim, and what I wanted to achieve was something like this:

![](/content/images/2015/dapple_vscode.png)

In here you can code in [Visual Studio Code using the Solidty Extension in windows](http://juan.blanco.ws/solidity-contracts-in-visual-studio-code/), and run the tests, deployment, etc on your Docker container.

##The Steps
1. Install Docker (Docker tool box) from https://docs.docker.com/engine/installation/windows/, and follow the instructions to configuere docker-machine and enviroment variables.

2. Once ready you should be able to run your container like:
`docker run -d -v /c/Users/{Your project folder}:/Projects -p 4001:4001 -p 5001:5001 -p 8000:8000 -p 8080:8080 -p 2121:21 -p 2222:22 -p 30000-30009:30000-30009 -p 30303:30303 -p 9000:8545 --name ethdev juanfranblanco/dapple`

A bit of explanation: 
* run will create and start your container
* -d will start your container dettached (it will run in the background)
* -v will mount a volume in your container, docker toolbox / boot2docker mounts automatically the c:/users folder in the host vm so we can use /c/Users/... and map it and moount to a folder called  :/Projects (Change this to whatever you like)
* -p is the mapping of ports exposed fore example ftp 21 is 2121, ssh 22 is 2222
* - name is our friendly container name
* and finally juanfranblanco/dapple is the image to download from docker hub.

3. Install Putty if not already and ssh to your machine using port 2222.
  To find out the ip address of your vm run
 `docker-machine ls`
and use the ip address of default to connect to the machine.
The user is *dev* and the password is *nexus*

