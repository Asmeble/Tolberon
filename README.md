# Tolberon
This repository contains information for the smallest standup possible using {docker, python, gcc, assembly, and unicorn-engine}. 

The follwing command {docker run -it --rm -v /var/run/docker.sock:/var/run/docker.sock --privileged ubuntu:latest sh -c "apt-get update && apt-get -y install python3 python3-pip gcc docker.io && python3 -m pip install unicorn && docker export -o \$(hostname).tar \$(hostname) && docker import \$(hostname).tar username/prebuilt_test:t0 && docker login | docker push username/prebuilt_test:t0 && docker rmi -f username/prebuilt_test:t0"} will create and publish a copy of itself and push to {hub.docker.com}, and then delete itself from the local runtime.

The follwing command {docker run -it -v /var/run/docker.sock:/var/run/docker.sock prebuilt_test:t0 bash} will give you a terminal with all the tools to break away from Kubernetes while retaining the relevant functionality. 
