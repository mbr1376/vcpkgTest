# vcpkgTest
## use vcpkg Manager for  c++ code in  cmake
vcpkg is a free C/C++ package manager for acquiring and managing libraries. Choose from over 1500 open source libraries to download and build in a single step or add your own private libraries to simplify your build process. Maintained by the Microsoft C++ team and open source contributors. 

1- create new aplication  in  directory project , create 2  file  json vcpkg.json  and   vcpkg-configuration.json
```bash
vcpkg new --application
```

2- add library dependency
```bash
vcpkg add port fmt
```
3- create file CMakePresets.json
```json
{
  "version": 2,
  "configurePresets": [
    {
      "name": "default",
      "generator": "Ninja",
      "binaryDir": "${sourceDir}/build",
      "cacheVariables": {
        "CMAKE_TOOLCHAIN_FILE": "$env{VCPKG_ROOT}/scripts/buildsystems/vcpkg.cmake"
      }
    }
  ]
}
```
4- run cmake 

```bash
cmake --preset=default
```
**Note: set VCPKG_ROOT=/path/to/vcpkg and set permision Directory**
```bash
export VCPKG_ROOT=/path/to/vcpkg
export PATH=$VCPKG_ROOT:$PATH

```
5- run cmake build
```bash
cmake --build build
```
