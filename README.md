Tested on Ubuntu 16.04 LTS

## How to build

* Install Protocol Buffers. [Here's instruction](https://github.com/google/protobuf/blob/master/src/README.md)
* Install gRPC. See [INSTALL](https://github.com/grpc/grpc/blob/master/INSTALL.md) for installation instructions
* Change CMAKE_PREFIX_PATH variable in CMakeFiles.txt[10] according to your install prefixes
* And build it
  ```bash
  mkdir build
  cd build
  cmake ..
  make
  ```
