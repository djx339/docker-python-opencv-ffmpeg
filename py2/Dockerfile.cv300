FROM ubuntu:16.04
MAINTAINER Daniel D <djx339@gmail.com>

ENV OPENCV_VERSION 3.0.0

RUN apt-get update && apt-get install -y --no-install-recommends \
            build-essential \
            cmake \
            git \
            libavcodec-dev \
            libavformat-dev \
            libdc1394-22-dev \
            libgtk2.0-dev \
            libjasper-dev \
            libjpeg-dev \
            libpng-dev \
            libswscale-dev \
            libtbb-dev \
            libtbb2 \
            libtiff-dev \
            pkg-config \
            python-pip \
            python2.7 \
            python2.7-dev \
            wget \
    && pip install -U pip setuptools wheel \
    && apt-get purge -y python-pip \
    && hash -r \
    && pip install numpy \
    && git clone --depth 1 --branch ${OPENCV_VERSION} https://github.com/Itseez/opencv.git /tmp/opencv \
    && git clone --depth 1 --branch ${OPENCV_VERSION} https://github.com/opencv/opencv_contrib.git /tmp/opencv_contrib \
    && mkdir /tmp/opencv/build \
    && cd /tmp/opencv/build \
    && cmake -D CMAKE_BUILD_TYPE=RELEASE \
      -D BUILD_PYTHON_SUPPORT=ON \
      -D CMAKE_INSTALL_PREFIX=/usr/local \
      -D OPENCV_EXTRA_MODULES_PATH=/tmp/opencv_contrib/modules \
      -D BUILD_EXAMPLES=OFF \
      -D WITH_IPP=OFF \
      -D WITH_FFMPEG=ON \
      -D WITH_V4L=ON .. \
    && make -j$(nproc) && make install && ldconfig \
    && apt-get remove -y \
        build-essential cmake git libatlas-base-dev gfortran \
        libjasper-dev libgtk2.0-dev libavcodec-dev libavformat-dev \
        libswscale-dev libjpeg-dev libpng-dev libtiff-dev libjasper-dev libv4l-dev \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* \
    && rm -rf /tmp/opencv \
    && rm -rf /tmp/opencv_contrib



