<style>
.md0{margin-top: 150px;}
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.md4{margin-top: 10px;}
.tbl1 td#header{background-color: D1ECCF}
.tbl1 tr#header{background-color: D1ECCF}
</style>


# [<span style="color:black;">Docker Script</span>](Docker.md)
[Basic](Docker-Basic.md) | 
[Structure](Docker-Structure.md) | 
[Command](Docker-Command.md) |
[Script](Docker-Script.md)





<div class="md1"></div>

## Create image from Dockerfile

    vim Dockerfile
    -----------------------------
    FROM ubuntu
    RUN mkdir DockerForMe
    
    docker build . -t myimage    
    docker run -it -d myimage 





<div class="md1"></div>

## Add volume to container

    docker run -it --name nginx -v /myvolume:/nginx nginx /bin/bash





<div class="md1"></div>

## Tow container with a same network

    docker network create my_local
    docker run -it -d --name alpine --network my_local alpine sh
    docker run -it -d --name ubuntu --network my_local ubuntu bash
    docker network inspect my_local

    docker exec -it alpine sh
    ping ubuntu

    docker exec -it ubuntu bash
    ping alpine