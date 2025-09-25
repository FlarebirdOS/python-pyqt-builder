pkgname=python-pyqt-builder
pkgver=1.18.2
pkgrel=1
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
sha256sums=(6060a9070b22078112ba0eb452e096bf9e149a740e15e6bd3a040c72b03db90a)

build() {
    cd PyQt-builder

    SETUPTOOLS_SCM_PRETEND_VERSION=${pkgver} python3 -m build --wheel --no-isolation
}

package() {
    cd PyQt-builder

    python3 -m installer -d ${pkgdir} dist/*.whl
}
