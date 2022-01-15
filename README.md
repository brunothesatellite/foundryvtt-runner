# Foundry Virtual Tabletop Runner 
Easy docker image for [Foundry Virtual Tabletop](https://foundryvtt.com/).\
See DockerHub [batiwo/foundryvtt-runner](https://hub.docker.com/r/batiwo/foundryvtt-runner)

## 1. Usage
This repository aims to describe a docker image intended to be used as "a plug'n'play" runtime environment for [Foundry Virtual Tabletop](https://foundryvtt.com/).

## 2. Run
This is image exposes the folling volumes :
- `/sources` : Means the installation folder (ex: `./FoundryVTT-X.XXX/resources/app/`). It should contains a `main.js` file at root.
- `/data` : Means the data folder where foundryvtt will store data. Recommanded to ensure data are persisted each time the container restart.

Commande:\
`docker run -p <exposed-port>:30000 -v <sources-path>:/sources -v <data-path>:/data batiwo/foundryvtt-runner:latest .`

Exemple for HTTP:\
`docker run --name foundryvtt -p 80:30000 /opt/foundryvtt/resources/app/:/sources -v /opt/foundryvtt-data/:/data batiwo/foundryvtt-runner:latest .`

## 3. Build
You can build this docker image yourself with the following command :\
`docker build -t foundryvtt-runner:latest .`
