# Script generated with Bloom
pkgdesc="ROS - ROS Python and C++ interfaces for universally unique identifiers."
url='http://ros.org/wiki/unique_id'

pkgname='ros-melodic-unique-id'
pkgver='1.0.6_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-melodic-catkin'
'ros-melodic-roscpp'
'ros-melodic-rospy'
'ros-melodic-rosunit'
'ros-melodic-uuid-msgs'
)

depends=('ros-melodic-roscpp'
'ros-melodic-rospy'
'ros-melodic-uuid-msgs'
)

conflicts=()
replaces=()

_dir=unique_id
source=()
md5sums=()

prepare() {
    cp -R $startdir/unique_id $srcdir/unique_id
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/melodic/setup.bash ] && source /opt/ros/melodic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/melodic \
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

