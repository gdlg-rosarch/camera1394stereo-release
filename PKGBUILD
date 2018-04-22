# Script generated with Bloom
pkgdesc="ROS - This is a modified version of the ROS driver for devices supporting the IEEE 1394 Digital Camera (IIDC) protocol in package camera1394. It adds support for reading from stereo pairs."
url='http://ros.org/wiki/camera1394stereo'

pkgname='ros-kinetic-camera1394stereo'
pkgver='1.0.6_1'
pkgrel=1
arch=('any')
license=('LGPL'
)

makedepends=('libdc1394'
'ros-kinetic-camera-info-manager'
'ros-kinetic-catkin'
'ros-kinetic-dynamic-reconfigure'
'ros-kinetic-image-transport'
'ros-kinetic-nodelet'
'ros-kinetic-tf'
)

depends=('ros-kinetic-camera-info-manager'
'ros-kinetic-dynamic-reconfigure'
'ros-kinetic-image-transport'
'ros-kinetic-nodelet'
'ros-kinetic-tf'
)

conflicts=()
replaces=()

_dir=camera1394stereo
source=()
md5sums=()

prepare() {
    cp -R $startdir/camera1394stereo $srcdir/camera1394stereo
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

