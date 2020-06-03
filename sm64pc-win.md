# sm64pc

Build instructions for a Windows executable in Ubuntu, using MXE. Works in WSL (Ubuntu 18.04 LTS) as well.

## 1. Installing MXE
(a) `git clone https://github.com/mxe/mxe.git`

(b) Install required packages specified in https://mxe.cc/#requirements-debian

(c) `sudo mv mxe /opt/mxe`


## 2. Setting up MXE
(a) `cd /opt/mxe`

(b) `make sdl2 glew glfw3`. This may take a while.

(c) `nano ~/.profile`, add `export PATH=/opt/mxe/usr/bin:$PATH` to the bottom, save and restart.


## 3. Building sm64pc
(a) `git clone https://github.com/sm64pc/sm64pc.git --branch nightly --single-branch`

(b) `cd sm64pc`, rename a SM64 US ROM to `baserom.us.z64` and copy it to current directory

(c) Replace all occurences of `-no-pie` in Makefile to `-fno-pie`

(d) `make CROSS=i686-w64-mingw32.static- WINDOWS_BUILD=1 NO_BZERO_BCOPY=1`
