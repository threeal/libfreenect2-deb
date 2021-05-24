cmake_minimum_required(VERSION 3.10)

project(libfreenect2-dev)

add_subdirectory("libfreenect2")

set(CPACK_GENERATOR "DEB")
set(CPACK_DEBIAN_FILE_NAME DEB-DEFAULT)

set(CPACK_DEBIAN_PACKAGE_NAME "libfreenect2-dev")

set(CPACK_DEBIAN_PACKAGE_VERSION 0.2.0)

string(TIMESTAMP NOW "%s")
set(CPACK_DEBIAN_PACKAGE_RELEASE ${NOW})

set(CPACK_PACKAGE_DESCRIPTION_SUMMARY "Open source drivers for the Kinect for Windows v2 device")

set(CPACK_PACKAGE_DESCRIPTION
program to parse that grammar.  Once you are proficient with Bison, you
"Driver for Kinect for Windows v2 (K4W2) devices (release and developer
preview).

Note: libfreenect2 does not do anything for either Kinect for Windows v1
or Kinect for Xbox 360 sensors. Use libfreenect1 for those sensors.

If you are using libfreenect2 in an academic context, please cite our
work using the following DOI: DOI

If you use the KDE depth unwrapping algorithm implemented in the library,
please also cite this ECCV 2016 paper.

This driver supports:
- RGB image transfer
- IR and depth image transfer
- registration of RGB and depth images

Missing features:
- firmware updates (see issue #460 for WiP)

Watch the OpenKinect wiki at www.openkinect.org and the mailing list at
https://groups.google.com/forum/#!forum/openkinect for the latest
developments and more information about the K4W2 USB protocol.

The API reference documentation is provided here
https://openkinect.github.io/libfreenect2/.")

set(CPACK_DEBIAN_PACKAGE_MAINTAINER "Alfi Maulana <alfi.maulana.f@gmail.com>")
set(CPACK_DEBIAN_PACKAGE_HOMEPAGE "https://github.com/OpenKinect/libfreenect2")

set(CPACK_DEBIAN_PACKAGE_DEPENDS
  "libglfw3-dev, libturbojpeg0-dev, libusb-1.0-0-dev, libva-dev, ocl-icd-opencl-dev")

include(CPack)
