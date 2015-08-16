# Contributer: Jo De Boeck <grimpy.reaper@gmail.com>

pkgname="mercurial-reviewboard-hg"
pkgver=222
pkgrel=1
pkgdesc="Mercurial extension for reviewboard"
url="http://mercurial.selenic.com/wiki/ReviewboardExtension"
license=("MIT")
arch=("i686" "x86_64")
depends=("mercurial")
makedepends=("mercurial")
provides=("mercurial-reviewboard")
source=()
md5sums=()

_hgroot="http://bitbucket.org/haard"
_hgrepo="mercurial-reviewboard"

build() {
	cd ${srcdir}

	# update the repo, else clone a new one
	if [ -d ${_hgrepo} ]; then
		cd ${_hgrepo}
		hg pull -u
	else
		hg clone ${_hgroot}/${_hgrepo}
		cd ${_hgrepo}
	fi
    python2 setup.py install --root=${pkgdir} --optimize=1
    rm ${pkgdir}/usr/bin/distribute_setup.py

}
