- we modify the CMakeLists.txt file to use the project() command to set both the project name and version number. When the project() command is called, CMake defines Tutorial_VERSION_MAJOR and Tutorial_VERSION_MINOR behind the scenes.
     > project(Tutorial VERSION 1.0)

- Then we used configure_file() to copy the input file with the specified CMake variables replaced:
  > configure_file(TutorialConfig.h.in TutorialConfig.h)

- Since the configured file will be written into the project binary directory, we must add that directory to the list of paths to search for include files.We used target_include_directories() to specify where the executable target should look for include files.
  > target_include_directories(Tutorial PUBLIC
                           "${PROJECT_BINARY_DIR}"
                           )

- Next, we need to modify tutorial.cxx to include the configured header file, TutorialConfig.h.
  > #include "TutorialConfig.h"


