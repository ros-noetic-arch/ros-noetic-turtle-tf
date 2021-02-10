# Script generated with import_catkin_packages.py.
# For more information: https://github.com/bchretien/arch-ros-stacks.
pkgdesc="ROS - turtle_tf demonstrates how to write a tf broadcaster and listener with the turtlesim."
url='https://wiki.ros.org/turtle_tf'

pkgname='ros-noetic-turtle-tf'
pkgver='0.2.3'
_pkgver_patch=0
arch=('i686' 'x86_64' 'aarch64' 'armv7h' 'armv6h')
pkgrel=1
license=('BSD')

ros_makedepends=(
	ros-noetic-turtlesim
	ros-noetic-catkin
	ros-noetic-tf
	ros-noetic-std-msgs
	ros-noetic-roscpp
	ros-noetic-rospy
	ros-noetic-geometry-msgs
)

makedepends=(
	'cmake'
	'ros-build-tools'
	${ros_makedepends[@]}
)

ros_depends=(
	ros-noetic-turtlesim
	ros-noetic-tf
	ros-noetic-std-msgs
	ros-noetic-roscpp
	ros-noetic-rospy
	ros-noetic-geometry-msgs
)

depends=(
	${ros_depends[@]}
)

_dir="geometry_tutorials-${pkgver}/turtle_tf"
source=("${pkgname}-${pkgver}.tar.gz"::"https://github.com/ros/geometry_tutorials/archive/${pkgver}.tar.gz")
sha256sums=('7346c3a2d595cbac3d4d2f2e5aa01ff2c7fbafe1c21374efb09244629303ea2f')

build() {
	# Use ROS environment variables.
	source /usr/share/ros-build-tools/clear-ros-env.sh
	[ -f /opt/ros/noetic/setup.bash ] && source /opt/ros/noetic/setup.bash

	# Create the build directory.
	[ -d ${srcdir}/build ] || mkdir ${srcdir}/build
	cd ${srcdir}/build

	# Build the project.
	cmake ${srcdir}/${_dir} \
		-DCATKIN_BUILD_BINARY_PACKAGE=ON \
		-DCMAKE_INSTALL_PREFIX=/opt/ros/noetic \
		-DPYTHON_EXECUTABLE=/usr/bin/python \
		-DSETUPTOOLS_DEB_LAYOUT=OFF
	make
}

package() {
	cd "${srcdir}/build"
	make DESTDIR="${pkgdir}/" install
}
