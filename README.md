# docker ros


## Pulling ROS images
    docker pull ros
    docker pull ros:kinetic-robot

## Running ROS containers
    docker run -it ros
    docker ps -l
    docker exec -it nostalgic_morse bash

## login as yourself
    docker run -it \
        --user=$(id -u $USER):$(id -g $USER) \
        --env="DISPLAY" \
        --volume="/etc/group:/etc/group:ro" \
        --volume="/etc/passwd:/etc/passwd:ro" \
        --volume="/etc/shadow:/etc/shadow:ro" \
        --volume="/etc/sudoers.d:/etc/sudoers.d:ro" \
        --volume="/tmp/.X11-unix:/tmp/.X11-unix:rw" \
        osrf/ros:kinetic-desktop-full \
        rqt

## Share your home directory
    docker run -it \
        --user=$(id -u $USER):$(id -g $USER) \
        --env="DISPLAY" \
        --workdir="/home/$USER" \
        --volume="/home/$USER:/home/$USER" \
        --volume="/etc/group:/etc/group:ro" \
        --volume="/etc/passwd:/etc/passwd:ro" \
        --volume="/etc/shadow:/etc/shadow:ro" \
        --volume="/etc/sudoers.d:/etc/sudoers.d:ro" \
        --volume="/tmp/.X11-unix:/tmp/.X11-unix:rw" \
        osrf/ros:kinetic-desktop-full \
        rqt


## ref
http://wiki.ros.org/docker/Tutorials/Docker

http://wiki.ros.org/es/docker/Tutorials/GUI

http://wiki.ros.org/es/docker/Tutorials/Compose