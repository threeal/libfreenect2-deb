# Libfreenect2 Debian Package

[![repository size](https://img.shields.io/github/repo-size/threeal/libfreenect2-deb)](https://github.com/threeal/libfreenect2-deb/pulse)
[![license](https://img.shields.io/github/license/threeal/libfreenect2-deb)](./LICENSE)
[![test status](https://img.shields.io/github/workflow/status/threeal/libfreenect2-deb/Build%20Debian%20Test?label=test)](https://github.com/threeal/libfreenect2-deb/actions)
[![deploy status](https://img.shields.io/github/workflow/status/threeal/libfreenect2-deb/Deploy%20Debian?label=deploy)](https://repository.ichiro-its.org/)

This project contains a [CPack](https://cmake.org/cmake/help/latest/module/CPack.html) build workspace of the [libfreenect2](https://github.com/OpenKinect/libfreenect2/).
This project is created to simplify the deployment of the library as a [Debian package](https://wiki.debian.org/Packaging).

## Usage

### Updating the Source Code

- Initialize the submodule and pull the latest commits.
  ```bash
  $ git submodule update --init --recursive
  ```
- Modify the CPack configuration in the [CMakeLists.txt](./CMakeLists.txt) according to the current source code information.
  > See [this guide](https://cmake.org/cmake/help/latest/cpack_gen/deb.html) for more information on CPack configuration for Debian package.

### Building the Project

- Create a build directory and move to it.
  ```bash
  $ mkdir build
  $ cd build
  ```
- Configure the CMake with the following options.
  ```bash
  $ cmake -DCMAKE_INSTALL_PREFIX=/usr ..
  ```
- Build the project.
  ```bash
  $ make
  ```
  > Optionally, you could speed up the build process by specifying the parallel job using `-j` option, see [this](https://www.gnu.org/software/make/manual/html_node/Parallel.html).
- Create a Debian package.
  ```bash
  $ make package
  ```

## License

This project is maintained by [Alfi Maulana](https://threeal.github.io/) and licensed under the [MIT LICENSE](./LICENSE)
