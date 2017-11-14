# How to run using docker

docker build -t matelight .
docker run -it --device=/dev/bus/usb/002/015 --security-opt seccomp=unconfined matelight
