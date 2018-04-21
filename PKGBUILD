# Script generated with Bloom
pkgdesc="ROS - slam_gmapping contains a wrapper around gmapping which provides SLAM capabilities."
url='http://ros.org/wiki/slam_gmapping'

pkgname='ros-lunar-slam-gmapping'
pkgver='1.3.10_1'
pkgrel=1
arch=('any')
license=('CreativeCommons-by-nc-sa-2.0'
)

makedepends=('ros-lunar-catkin'
)

depends=('ros-lunar-gmapping'
'ros-lunar-openslam-gmapping'
)

conflicts=()
replaces=()

_dir=slam_gmapping
source=()
md5sums=()

prepare() {
    cp -R $startdir/slam_gmapping $srcdir/slam_gmapping
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

