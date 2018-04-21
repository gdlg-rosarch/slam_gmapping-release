# Script generated with Bloom
pkgdesc="ROS - This package contains a ROS wrapper for OpenSlam's Gmapping. The gmapping package provides laser-based SLAM (Simultaneous Localization and Mapping), as a ROS node called slam_gmapping. Using slam_gmapping, you can create a 2-D occupancy grid map (like a building floorplan) from laser and pose data collected by a mobile robot."
url='http://ros.org/wiki/gmapping'

pkgname='ros-lunar-gmapping'
pkgver='1.3.10_1'
pkgrel=1
arch=('any')
license=('CreativeCommons-by-nc-sa-2.0'
)

makedepends=('ros-lunar-catkin>=0.5.68'
'ros-lunar-nav-msgs'
'ros-lunar-nodelet'
'ros-lunar-openslam-gmapping'
'ros-lunar-roscpp'
'ros-lunar-rostest'
'ros-lunar-tf'
)

depends=('ros-lunar-nav-msgs'
'ros-lunar-nodelet'
'ros-lunar-openslam-gmapping'
'ros-lunar-roscpp'
'ros-lunar-tf'
)

conflicts=()
replaces=()

_dir=gmapping
source=()
md5sums=()

prepare() {
    cp -R $startdir/gmapping $srcdir/gmapping
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/lunar/setup.bash ] && source /opt/ros/lunar/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/lunar \
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

