# LHCI Server
A Lighthouse CI Server with SSH support.

## Setup

Pull Git repository. 

Change directory to repostory. 

Build image

````shell
docker image build -t lhci .
````

Create volume

````shell
docker volume create lhci-data
````

Run Container

````shell
docker container run -e ROOT_PASSWORD=MyPassword --publish 9001:9001 --publish 2222:22 --mount='source=lhci-data,target=/data' --detach lhci
```` 

## Usage

SSH into the container

````shell
ssh root@localhost -p 2222
````