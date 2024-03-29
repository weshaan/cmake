Create a file named CMakeLists.txt in the root directory of your project. Open CMakeLists.txt in a text editor and define your project. Here's a minimal example for a C++ project:
 
- Specify the minimum version of CMake required

> cmake_minimum_required(VERSION 3.10)

- Set the project name and version

> project(MyProject VERSION 1.0)

- Add an executable target

> add_executable(my_executable main.cpp)
