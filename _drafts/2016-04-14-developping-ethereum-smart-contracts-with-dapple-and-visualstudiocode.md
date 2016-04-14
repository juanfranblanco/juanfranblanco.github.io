---
layout: post
title: Developing Smart Contracts in Ethereum with Dapple and Visual Studio Code in Windows with Docker.
date: '2016-04-14 04:49:04'
---

Dapple from its origins as Python tool to its current implementation in node.js has fascinated me. With dapple you can unit test your Ethereum Solidty contracts using Solidity, the same way as if you test C# code with C# Code, Javascript, etc.
But dapple is not just limited to testing, it allows you to, install, package and deploy and bundle scripts.

But installing Dapple in Windows, has been always an issue, similar to Ethereum, there are lots of hurdles to get through due to the different dependencies.

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

Coding using Vim inside Docker can be a dunting experience if you are not used to Vim, and what I want to achive is something like this:

![](/content/images/2015/dapple_vscode.png)

In here you can code in [Visual Studio Code using the Solidty Extension in windows](http://juan.blanco.ws/solidity-contracts-in-visual-studio-code/), and run the tests, deployment, etc on your Docker container.

