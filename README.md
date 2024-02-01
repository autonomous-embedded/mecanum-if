# Protocol Buffers
Protocol Buffers is a language and platform-neutral, extensible mechanism similar to XML or JSON. This developed by Google method is used to serialize structured data for use in communications protocols, data storage, and more. For more information about Protocol Buffers, refer to the [official documentation](https://developers.google.com/protocol-buffers).

## Utilization in project
Protocol Buffers is used in this project to define the message format for the communication between the Jetson Orin NX and the Omni4WD Nexus platform (with Arduino Diecimila, ATMega 328). The message format is defined in the `mecanum.proto` file located in the `mecanum-if/protobuf` directory.

## How to generate sources using Protocol Buffers (protobuf)

### Generating C++ sources on the Jetson Orin NX

#### Installing the `protoc` Tool
If the `protoc` tool is not installed on your system, you can install it using the following command:
```bash
sudo apt-get update
sudo apt-get install protobuf-compiler
```

#### Generating C++ Sources
1. Navigate to the `mecanum-if/protobuf` directory containing the `mecanum.proto` file.
2. Generate C++ sources by running the following command:
```bash
protoc --proto_path=. --cpp_out=. mecanum.proto
```
- The `--proto_path` flag specifies the directory in which the `mecanum.proto` file is located.
- The `--cpp_out` flag specifies the directory in which the generated C++ sources will be placed.
- The `mecanum.proto` file is the name of the `.proto` file to be compiled.
3. The generated C++ sources will be placed in the `mecanum-if/protobuf` directory.
4. The generated C++ sources can be used in your C++ program by including the `mecanum.pb.h` header,
    - if the `mecanum.pb.cc` source file is compiled and linked with your program.

#### Generating Python Sources
1. Navigate to the `mecanum-if/protobuf` directory containing the `mecanum.proto` file.
2. Generate Python sources by running the following command:
```bash
protoc --proto_path=. --python_out=. mecanum.proto
```
3. The generated Python sources will be placed in the `mecanum-if/protobuf` directory.
4. The generated Python sources can be used in your Python program by importing the `mecanum_pb2` module.
```python
import mecanum_pb2
```
