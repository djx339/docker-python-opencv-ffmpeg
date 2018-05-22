# docker-python-opencv-ffmpeg
[![Build Status](https://travis-ci.org/djx339/docker-python-opencv-ffmpeg.svg?branch=master)](https://travis-ci.org/djx339/docker-python-opencv-ffmpeg)

Docker Image for OpenCV With FFMPEG

Includes:
  - Python
  - OpenCV
  - FFMPEG

## Versions

**Python2**

[`py2-cv3.0.0` (py2/Dockerfile.cv300)](py2/Dockerfile.cv300)

[`py2-cv3.1.0` (py2/Dockerfile.cv310)](py2/Dockerfile.cv310)

[`py2-cv3.2.0` (py2/Dockerfile.cv320)](py2/Dockerfile.cv320)

[`py2-cv3.3.0` (py2/Dockerfile.cv330)](py2/Dockerfile.cv330)

[`py2-cv3.4.0`, `latest` (py2/Dockerfile.cv340)](py2/Dockerfile.cv340)

**Python3**

[`py3-cv3.0.0`(py3/Dockerfile.cv300)](py3/Dockerfile.cv300)

[`py3-cv3.1.0`(py3/Dockerfile.cv310)](py3/Dockerfile.cv310)

[`py3-cv3.2.0`(py3/Dockerfile.cv320)](py3/Dockerfile.cv320)

[`py3-cv3.3.0`(py3/Dockerfile.cv330)](py3/Dockerfile.cv330)

[`py3-cv3.4.0`(py3/Dockerfile.cv340)](py3/Dockerfile.cv340)

## Usage 

```shell
docker run -it --rm djx339/docker-python-opencv-ffmpeg:py2-cv3.1.0 python
>>> import cv2
>>> cv2.VideoCapture('/path/to/your/video.mp4').read()
```
