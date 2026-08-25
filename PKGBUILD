# ryzen_monitor_ng Author plasmin
# PKGBUILD Author Dustin Arnett <dustovich@outlook.com>

pkgname=ryzen_monitor_ng-git
_pkgname=ryzen_monitor_ng
pkgver=r16.d62a430
pkgrel=1
arch=('x86_64')
options=(!strip !debug)
pkgdesc="Monitor power information of Ryzen processors via the PM table of the SMU."
url="https://github.com/plasmin/ryzen_monitor_ng"
license=('AGPL-3.0-or-later')
makedepends=('git')
depends=('ryzen_smu')
provides=('ryzen_monitor_ng')
conflicts=('ryzen_monitor_ng')
source=("git+${url}.git")
sha256sums=('SKIP')

pkgver() {
  cd "$srcdir/$_pkgname"
  ( set -o pipefail
    git describe --long --abbrev=7 2>/dev/null | sed 's/\([^-]*-g\)/r\1/;s/-/./g' ||
    printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short=7 HEAD)"
  )
}

build() {
  cd "${_pkgname}"
  make
}

package() {
  install -Dm644 "${_pkgname}/LICENSE" "${pkgdir}/usr/share/licenses/${pkgname}/license.txt"
  install -Dm755 "${_pkgname}/src/ryzen_monitor" "${pkgdir}/usr/bin/${_pkgname}"
}
