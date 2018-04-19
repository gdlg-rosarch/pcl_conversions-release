# Script generated with Bloom
pkgdesc="ROS - Provides conversions from PCL data types and ROS message types"
url='http://wiki.ros.org/pcl_conversions'

pkgname='ros-kinetic-pcl-conversions'
pkgver='0.2.1_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('pcl'
'ros-kinetic-catkin'
'ros-kinetic-cmake-modules'
'ros-kinetic-pcl-msgs'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
)

depends=('pcl'
'ros-kinetic-pcl-msgs'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
)

conflicts=()
replaces=()

_dir=pcl_conversions
source=()
md5sums=()

prepare() {
    cp -R $startdir/pcl_conversions $srcdir/pcl_conversions
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

