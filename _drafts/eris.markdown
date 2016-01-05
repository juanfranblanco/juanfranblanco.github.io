---
layout: post
title: Building Ethereum Solidity contracts with Eris on Windows
---

This is a summary of steps I have followed to get up and running in Windows with Eris to build Ethereum Solidity contracts.

## What is Eris?
"Eris is free software that allows anyone to build their own secure, low-cost, run-anywhere data infrastructure using blockchain and smart contract technology."

Here is also a great presentation (long)
<iframe width="560" height="315" src="https://www.youtube.com/embed/XB0pHaghPIg" frameborder="0" allowfullscreen></iframe>

and their short introduction

<iframe width="560" height="315" src="https://www.youtube.com/embed/raCexydDa0o" frameborder="0" allowfullscreen></iframe>

## Getting Started
These are the main instructions at Eris web site https://docs.erisindustries.com/

###Installing Docker Toolbox
The simplest and fastest to get ready is to use Docker, Docker is linux based, so in Windows you need to install Docker toolbox which it includes VirtualBox. 
You can downloaded from here: https://www.docker.com/toolbox
Once downloaded open the command prompt and run
```
docker version
````

## Install Go 
* You can install [Go using Chocolatey](https://chocolatey.org/packages?q=go)

```
choco install golang
```

* Make sure your GOPATH is set for example
```
set GOPATH=c:\users\yourusername\gopath
```

## Eris
* Download Eris using go
```
go get github.com/eris-ltd/eris-cli/cmd/eris
```
* Set the %PATH located in %GOPATH%/bin and run
```
* Initalise Eris
eris init
```
* Now dowload epm , Eris package manager
```
go get github.com/eris-ltd/eris-pm/cmd/epm
```
* Initialise EPM
```
epm init
```
* 
