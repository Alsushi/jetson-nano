FROM nvcr.io/nvidia/l4t-base:r32.3.1
LABEL MAINTAINER: Etienne LEROY
RUN apt-get update -y 
RUN apt-get install python3-pip -y 
RUN pip3 install -U pip
RUN DEBIAN_FRONTEND=noninteractive apt-get install libhdf5-serial-dev hdf5-tools libhdf5-dev zlib1g-dev zip libjpeg8-dev -y
RUN DEBIAN_FRONTEND=noninteractive apt-get install python3 python-dev python3-dev build-essential libssl-dev libffi-dev libxml2-dev libxslt1-dev zlib1g-dev -yq
RUN pip3 install -U numpy grpcio absl-py py-cpuinfo psutil portpicker six mock requests gast h5py astor termcolor protobuf keras-applications keras-preprocessing wrapt google-pasta
RUN pip3 install --pre --extra-index-url https://developer.download.nvidia.com/compute/redist/jp/v42 tensorflow-gpu==2.0.0+nv19.11

# freetype2 dependancies
RUN apt-get install libpng-tools libpng16-16 libpng-dev
# matplotlib dependancies freetype2 headers
RUN wget http://ftp.de.debian.org/debian/pool/main/f/freetype/libfreetype6_2.9.1-3+deb10u1_arm64.deb
RUN dpkg -i libfreetype6_2.9.1-3+deb10u1_arm64.deb
RUN wget http://ftp.de.debian.org/debian/pool/main/f/freetype/libfreetype6-dev_2.9.1-3+deb10u1_arm64.deb
RUN dpkg -i libfreetype6-dev_2.9.1-3+deb10u1_arm64.deb
# TF tutorial packages
RUN pip3 install -U Cython contextlib2 pillow lxml jupyter matplotlib
RUN apt-get install protobuf-compiler python-pil python-lxml python-tk
