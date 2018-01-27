# How to run using docker

Build it:

docker build -t matelight .

Then run it:

docker run -it --device=/dev/bus/usb/002/015 -p 1337:1337 -p 1337:1337/udp --security-opt seccomp=unconfined matelight

or

docker run -it --device=/dev/bus/usb/ -p 1337:1337 -p 1337:1337/udp --security-opt seccomp=unconfined matelight
