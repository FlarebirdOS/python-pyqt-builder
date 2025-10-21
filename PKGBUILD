pkgname=python-pyqt-builder
pkgver=1.19.0
pkgrel=2
pkgdesc="The PEP 517 compliant PyQt build system"
arch=('x86_64')
url="https://pypi.org/project/PyQt-builder"
license=('BSD-2-Clause')
depends=(
    'python'
    'python-packaging'
    'python-sip'
)
makedepends=(
    'git'
    'python-build'
    'python-installer'
    'python-setuptools-scm'
    'python-wheel'
)
source=(git+ssh://git@github.com/Python-PyQt/PyQt-builder#tag=${pkgver})
sha256sums=(16eeb5531721fa8604ddf4c64fa0fc5d494181566536011b44a08d88dc9e6156)

build() {
    cd PyQt-builder

    SETUPTOOLS_SCM_PRETEND_VERSION=${pkgver} python3 -m build --wheel --no-isolation
}

package() {
    cd PyQt-builder

    python3 -m installer -d ${pkgdir} dist/*.whl
}
