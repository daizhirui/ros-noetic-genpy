# Script generated with import_catkin_packages.py.
# For more information: https://github.com/bchretien/arch-ros-stacks.
pkgdesc="ROS - Python ROS message and service generators."
url='https://wiki.ros.org/genpy'

pkgname='ros-noetic-genpy'
pkgver='0.6.16'
arch=('any')
pkgrel=1
license=('BSD')

ros_makedepends=(
	ros-noetic-genmsg
	ros-noetic-catkin
)

makedepends=(
	'cmake'
	'ros-build-tools'
	${ros_makedepends[@]}
)

ros_depends=(
	ros-noetic-genmsg
)

depends=(
	${ros_depends[@]}
	python-yaml
)

_commit="f70658f2200dfb7c98e99e9cf15be61cfaa1a432"
_dir="genpy-${_commit}/"
source=("${pkgname}-${pkgver}.tar.gz"::"https://github.com/ros/genpy/archive/${_commit}.tar.gz")
sha256sums=('c3c38ef5dcdbcf0482d377c60f87d60ef04f977ad4954a8a43ae4685a250aa0a')

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
