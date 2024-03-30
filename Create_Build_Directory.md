working in bash: 
- Create a separate directory (usually named build) where CMake will generate build files:
  
   > mkdir build </br>
   > cd build

- Inside the build directory, run CMake and specify the path to the source directory:
   > cmake ..
- After running CMake, you can now build your project using the generated build files. The exact commands depend on your platform and the generator used by CMake. For example, on Unix-like systems with Makefiles generated:
  > make
