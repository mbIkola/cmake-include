# cmake-include
Few cmake commands, functions and targets which may be usable in all cmake projects. Includes DownloadProject, ConfigSafeGuard and probably something else. Expected to be included into project as submodule

You probably visit this page by mistake and do not need this repo. 

# WHY

Cuz i have no idea how to deal with cmake dependencies. 

# How to

1. In root folder of your project simply run:

```
$ git submodule add git@github.com:mbIkola/cmake-include.git ./cmake
```

2. Use one of scenarios/functions in your project. Example usage for google-test (file test/CMakeLists.txt)

```
include(DownloadProject)

download_project(
        PROJ                googletest
        GIT_REPOSITORY      https://github.com/google/googletest.git
        GIT_TAG             master
        UPDATE_DISCONNECTED 1
)

add_subdirectory(${googletest_SOURCE_DIR} ${googletest_BINARY_DIR} EXCLUDE_FROM_ALL)

```

