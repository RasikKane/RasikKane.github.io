---
title: Docker for windows 10 home
date: 2020-09-24 14:41:57 Z
categories:
- machine-learning
tags:
- Containerized Applications
- Data Science [DS]
- Linux
- Bash
layout: post
comments: true
description: Installation and launching docker with on Windows 10 home
author: Rasik Kane
---

**Doker is multi-platform compatible software packaging tool, which is efficient way to roll out containerised applications**
* Web apps developers and ML engineers use dockers extensively for [CI-CD](https://www.docker.com/blog/best-practices-for-using-docker-hub-for-ci-cd/) 

# Docker
A [Docker container image](https://www.docker.com/resources/what-container) is a lightweight, standalone, executable package of software.
* It includes everything needed to run an application: code, runtime, system tools, system libraries and settings.
* containers - images become containers when they run on Docker Engine
* Containers isolate software from its environment and ensure that it works uniformly despite differences for instance between development and staging.

<br>


## Installation on windows 10 Home

### Step 1 : System requirements
* Ensure that you ae running Windows 10 ***home***
  * As of Jan 2021, For x64 systems: Version 1903 or higher, with Build 18362 or higher.
* To check version, start run mode:
```windows-R```
* Then type and enter:
```winver```
* Latest update for windows 10 home is available [here](https://www.microsoft.com/en-gb/software-download/windows10)

### step 2. Install WSL
Go to [WSL](https://docs.microsoft.com/en-us/windows/wsl/install-win10#step-1---enable-the-windows-subsystem-for-linux) and **Follow steps 1 - 5**

### Step 3.Download and install docker.exe
latest docker for windows 10 home can be found [here](https://desktop.docker.com/win/stable/Docker%20Desktop%20Installer.exe)

<br>

## Getting started : CRUD operations

### Create a container
launch you powershell / command prompt and create yuor environment.
* open sourced docker images can be pulled from [docker hub](https://hub.docker.com/) 
* The ```docker run``` command first creates a writeable container layer over the specified image, and then starts using it.
```powershell
docker run -tid --name [my_Container_Name] [docker_image_url]
```
* -t : Allocate a pseudo-tty
* -i : Keep STDIN open even if not attached
* -d : containers started in detached mode exit when the root process used to run the container exits

### Start a container
```powershell
docker start [my_container_name]
```

### List all containers
Container information including container ID, IMAGE, status, ports, name etc is displayed
```powershell
docker ps --all
```

### List only container IDs
```powershell
docker ps -aq
```

### Stop a container
```powershell
docker stop [my_container_name]
```

### remove a container
Ensure that container is already stopped using preivous commands 
```powershell
docker rm [my_container_name]
```

### stop all containers at once
To stop all containers are once, we can capture all container IDs into a shell variable and stop all containers in one go.
```powershell
docker stop $(docker ps -aq)
```

### remove all containers
Ensure that containers are already stopped using preivous commands 
```powershell
docker rm $(docker ps -aq)
```

## Operate with container

### Launch bash inside your linux based container
If insalled docker has a shell program [bash, mysql, mongo etc.] installed, it can launched as shown below.
```powershell
docker exec -it [my_container_name] bash
```
* docker run -i-t  enables us to detach with TTY (in this case, Bash) wih ctrl-P ctrl-Q and reattached with docker attach
* docker run -i → cannot be detached with ctrl-P ctrl-Q; will disrupt stdin
* docker run → cannot be detached with ctrl-P ctrl-Q; can SIGKILL client; can reattach with docker attach

### move files between docker container and local machine
```powershell
docker cp [my_Container_Name]:/[path_to_myFile] ./[local_machine_path]
```

