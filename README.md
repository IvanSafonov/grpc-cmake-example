Tested on Ubuntu 18.04 LTS

## How to build

* Install [Protocol Buffers](https://github.com/google/protobuf/blob/master/src/README.md) and [gRPC](https://github.com/grpc/grpc/tree/master/src/cpp)
  ```bash
  # On ubuntu 18.04
  sudo apt-get install build-essential autoconf libtool pkg-config automake curl
    
  git clone -b $(curl -L https://grpc.io/release) https://github.com/grpc/grpc
  cd grpc
  git submodule update --init
   
  # Build and install protobuf
  cd ./third_party/protobuf
  ./autogen.sh
  ./configure --prefix=/opt/protobuf
  make -j `nproc`
  sudo make install
    
  # Build and install gRPC
  cd ../..
  make -j `nproc` PROTOC=/opt/protobuf/bin/protoc 
  sudo make prefix=/opt/grpc install

  ```
* Change CMAKE_PREFIX_PATH variable in CMakeFiles.txt[7] according to your install prefixes
* And build it
```bash
  mkdir build
  cd build
  cmake ..
  make
```
