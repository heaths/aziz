# Contributing

This project uses [CMake](https://cmake.org) to configure build files for Windows. The following instructions assume you're building the project for x64.

## Prerequisites

* [CMake](https://cmake.org/download)
* [vcpkg](https://github.com/microsoft/vcpkg)
* [Visual Studio](https://www.visualstudio.com). Opening the project folder will provide additional recommendations, including:
  * Desktop Development with C++
  * C++ CMake tools for Windows
  * Windows 10 SDK (Recommended: 10.0.17763.0)
* (*Optional, though assumed in instructions below*) [Visual Studio Code](https://code.visualstudio.com/download). Opening the project folder will provide additional recommendations, including:
  * (*Required*) [CMake Tools extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cmake-tools)
  * (*Recommended*) [C/C++ extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools)

## Build

The following instructions show you how to build the project using [Visual Studio Code](https://code.visualstudio.com) with the [CMake Tools](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cmake-tools) extension.

1. After installing `vcpkg`, install cpprestsdk for your target platform:

   ```batch
   vcpkg install cpprestsdk:x64-windows`
   ```

2. Run `cmake` from within a "build" subdirectory that references the directory where you installed `vcpkg`, e.g. `c:\src\vcpkg`:

   ```batch
   mkdir build
   cd build
   cmake -DCMAKE_TOOLCHAIN_FILE=C:\src\vcpkg\scripts\buildsystems\vcpkg.cmake ..
   ```

3. Open the project root directory in Visual Studio code:

   ```batch
   code ..
   ```

4. After the CMake Tools extension completes project generation, press **Ctrl+F5** to build and debug the application.
