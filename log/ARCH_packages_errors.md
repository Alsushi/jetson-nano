
1. pip3 install matplotlib
```python
#error "FreeType version 2.3 or higher is required. \
          ^~~~~
    src/checkdep_freetype2.c:10:10: error: #include expects "FILENAME" or <FILENAME>
     #include FT_FREETYPE_H
              ^~~~~~~~~~~~~
    src/checkdep_freetype2.c:15:9: note: #pragma message: Compiling with FreeType version FREETYPE_MAJOR.FREETYPE_MINOR.FREETYPE_PATCH.
     #pragma message("Compiling with FreeType version " \
             ^~~~~~~
    src/checkdep_freetype2.c:18:4: error: #error "FreeType version 2.3 or higher is required. You may set the MPLLOCALFREETYPE environment variable to 1 to let Matplotlib download it."
       #error "FreeType version 2.3 or higher is required. \
        ^~~~~
    error: command 'aarch64-linux-gnu-gcc' failed with exit status 1
    ----------------------------------------
ERROR: Command errored out with exit status 1: /usr/bin/python3 -u -c 'import sys, setuptools, tokenize; sys.argv[0] = '"'"'/tmp/pip-install-o1wclrf1/matplotlib/setup.py'"'"'; __file__='"'"'/tmp/pip-install-o1wclrf1/matplotlib/setup.py'"'"';f=getattr(tokenize, '"'"'open'"'"', open)(__file__);code=f.read().replace('"'"'\r\n'"'"', '"'"'\n'"'"');f.close();exec(compile(code, __file__, '"'"'exec'"'"'))' install --record /tmp/pip-record-3wuf43fk/install-record.txt --single-version-externally-managed --compile --install-headers /usr/local/include/python3.6/matplotlib Check the logs for full command output.
```
1.1.1 pip3 install freetype2
ERROR: Could not find a version that satisfies the requirement freetype2 (from versions: none)
ERROR: No matching distribution found for freetype2
installfr

1.1.2 apt install libfreetype6
```bash
:/# apt install libfreetype6
Reading package lists... Done
Building dependency tree       
Reading state information... Done
libfreetype6 is already the newest version (2.8.1-2ubuntu2).
libfreetype6 set to manually installed.
0 upgraded, 0 newly installed, 0 to remove and 208 not upgraded.
```
1.1.3 wget http://ftp.de.debian.org/debian/pool/main/f/freetype/libfreetype6_2.9.1-3+deb10u1_arm64.deb
dpkg -i

wget http://ftp.de.debian.org/debian/pool/main/f/freetype/libfreetype6-dev_2.9.1-3+deb10u1_arm64.deb
dpkg -i

```bash
Selecting previously unselected package libfreetype6-dev:arm64.
(Reading database ... 48816 files and directories currently installed.)
Preparing to unpack libfreetype6-dev_2.9.1-3+deb10u1_arm64.deb ...
Unpacking libfreetype6-dev:arm64 (2.9.1-3+deb10u1) ...
dpkg: dependency problems prevent configuration of libfreetype6-dev:arm64:
 libfreetype6-dev:arm64 depends on libpng-dev; however:
  Package libpng-dev is not installed.

dpkg: error processing package libfreetype6-dev:arm64 (--install):
 dependency problems - leaving unconfigured
Errors were encountered while processing:
 libfreetype6-dev:arm64
```
root@jetson1:~/install# apt --fix-broken install
```bash
Reading package lists... Done
Building dependency tree       
Reading state information... Done
Correcting dependencies... Done
The following additional packages will be installed:
  libpng-dev libpng-tools libpng16-16
The following NEW packages will be installed:
  libpng-dev libpng-tools
The following packages will be upgraded:
  libpng16-16
1 upgraded, 2 newly installed, 0 to remove and 207 not upgraded.
1 not fully installed or removed.
Need to get 350 kB of archives.
After this operation, 668 kB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://ports.ubuntu.com/ubuntu-ports bionic-updates/main arm64 libpng16-16 arm64 1.6.34-1ubuntu0.18.04.2 [162 kB]
Get:2 http://ports.ubuntu.com/ubuntu-ports bionic-updates/main arm64 libpng-dev arm64 1.6.34-1ubuntu0.18.04.2 [165 kB]
Get:3 http://ports.ubuntu.com/ubuntu-ports bionic-updates/main arm64 libpng-tools arm64 1.6.34-1ubuntu0.18.04.2 [23.5 kB]
Fetched 350 kB in 0s (1107 kB/s)         
debconf: delaying package configuration, since apt-utils is not installed
(Reading database ... 48875 files and directories currently installed.)
Preparing to unpack .../libpng16-16_1.6.34-1ubuntu0.18.04.2_arm64.deb ...
Unpacking libpng16-16:arm64 (1.6.34-1ubuntu0.18.04.2) over (1.6.34-1ubuntu0.18.04.1) ...
Selecting previously unselected package libpng-dev:arm64.
Preparing to unpack .../libpng-dev_1.6.34-1ubuntu0.18.04.2_arm64.deb ...
Unpacking libpng-dev:arm64 (1.6.34-1ubuntu0.18.04.2) ...
Selecting previously unselected package libpng-tools.
Preparing to unpack .../libpng-tools_1.6.34-1ubuntu0.18.04.2_arm64.deb ...
Unpacking libpng-tools (1.6.34-1ubuntu0.18.04.2) ...
Setting up libpng16-16:arm64 (1.6.34-1ubuntu0.18.04.2) ...
Setting up libpng-tools (1.6.34-1ubuntu0.18.04.2) ...
Processing triggers for libc-bin (2.27-3ubuntu1) ...
Setting up libpng-dev:arm64 (1.6.34-1ubuntu0.18.04.2) ...
Setting up libfreetype6-dev:arm64 (2.9.1-3+deb10u1) ...
```
root@jetson1:~/install# dpkg -i libfreetype6-dev_2.9.1-3+deb10u1_arm64.deb 
```bash
(Reading database ... 48905 files and directories currently installed.)
Preparing to unpack libfreetype6-dev_2.9.1-3+deb10u1_arm64.deb ...
Unpacking libfreetype6-dev:arm64 (2.9.1-3+deb10u1) over (2.9.1-3+deb10u1) ...
Setting up libfreetype6-dev:arm64 (2.9.1-3+deb10u1) ...
```
root@jetson1:~/install# pip3 install matplotlib

```python
Collecting matplotlib
  Using cached matplotlib-3.2.1.tar.gz (40.3 MB)
Requirement already satisfied: cycler>=0.10 in /usr/local/lib/python3.6/dist-packages (from matplotlib) (0.10.0)
Requirement already satisfied: kiwisolver>=1.0.1 in /usr/local/lib/python3.6/dist-packages (from matplotlib) (1.2.0)
Requirement already satisfied: numpy>=1.11 in /usr/local/lib/python3.6/dist-packages (from matplotlib) (1.18.2)
Requirement already satisfied: pyparsing!=2.0.4,!=2.1.2,!=2.1.6,>=2.0.1 in /usr/local/lib/python3.6/dist-packages (from matplotlib) (2.4.7)
Requirement already satisfied: python-dateutil>=2.1 in /usr/local/lib/python3.6/dist-packages (from matplotlib) (2.8.1)
Requirement already satisfied: six in /usr/local/lib/python3.6/dist-packages (from cycler>=0.10->matplotlib) (1.14.0)
Building wheels for collected packages: matplotlib
  Building wheel for matplotlib (setup.py) ... - done
  Created wheel for matplotlib: filename=matplotlib-3.2.1-cp36-cp36m-linux_aarch64.whl size=11163929 sha256=a5daf2aac3ac5506926c85201411315487e2809331dad331affc426dd52c9c37
  Stored in directory: /root/.cache/pip/wheels/fd/41/73/65b5614bd690fdb2b8716c00fda249b6ad05321007a7547766
Successfully built matplotlib
Installing collected packages: matplotlib
Successfully installed matplotlib-3.2.1

```