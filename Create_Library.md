- In the CMakeLists.txt file in the MathFunctions directory, we create a library target called MathFunctions with add_library(). The source files for the library are passed as an argument to add_library(). This looks like the following line:
  > add_library(MathFunctions MathFunctions.cxx mysqrt.cxx)

- To make use of the new library we will add an add_subdirectory() call in the top-level CMakeLists.txt file so that the library will get built.
  > add_subdirectory(MathFunctions)

- Next, the new library target is linked to the executable target using target_link_libraries().
  > target_link_libraries(Tutorial PUBLIC MathFunctions)

- Finally we need to specify the library's header file location. Modify the existing target_include_directories() call to add the MathFunctions subdirectory as an include directory so that the MathFunctions.h header file can be found.
  >  target_include_directories(Tutorial PUBLIC
                          "${PROJECT_BINARY_DIR}"
                          "${PROJECT_SOURCE_DIR}/MathFunctions"
                          )

- Now let's use our library. In tutorial.cxx, include MathFunctions.h:
  > #include "MathFunctions.h"

