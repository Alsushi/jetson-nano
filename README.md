# Docker container with Tensorflow GPU for Jetson Nano

## Build docker image

Obviously, the mandatory step to use the container is to flash L4T on the SD-card. Afterward JetPack can be added - or NOT! - it will work **with & without** extra packages.
At first, you may install [Jetpack 4.3.1](https://developer.nvidia.com/embedded/jetpack) for Jetson Nano.

Next, set **nvidia runtime** as default for Your docker daemon.

In file */etc/docker/daemon.json* add line 
```
"default-runtime": "nvidia"
```


*/etc/docker/daemon.json* 
```
{
"default-runtime": "nvidia",
    "runtimes": {
        "nvidia": {
            "path": "nvidia-container-runtime",
            "runtimeArgs": []
        }
    }
}
```

When you set this, you can build the image using our Dockerfile with *docker build command*.

## Verify
To check if it's working correctly run container and import tensorflow in python3. 
If it's working fine, the result will be: 

```
$ docker run -it *<docker image name>* bash

root@3ff5d388cfc9:/# python3
Python 3.6.8 (default, Jan 14 2019, 11:02:34) 
[GCC 8.0.1 20180414 (experimental) [trunk revision 259383]] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import tensorflow as ts
>>> print(ts.__version__)
1.13.1
```
