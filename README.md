# docker-turing

## Alpine
This version currently ends in a segmentation Fault.


## Ubuntu
Current ubuntu version contains a boost version which is too old. 
Boost will be build from source repo.

Usage:
```
docker run  -v=/home/working/dir:/tmp/ffmpeg  vitecde/turing:ubuntu -i  input.mov -c:v libturing -turing-params speed=fast -strict -2 -y out.mp4'
```
