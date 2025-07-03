# Maintainer: Kara <krocat1147@gmail.com>
pkgname=udptunnel-deb
_pkgname=udptunnel
pkgver=1.1.1
_pkgver=1.1
pkgrel=1.4
_pkgrel=10
pkgdesc="tunnel UDP packets over a TCP connection"
arch=('x86_64')
url="http://www1.cs.columbia.edu/~lennox/udptunnel/"
license=('Unknown')
provides=('udptunnel')
depends=(
  'libnsl2'
  'glibc'
)
#install=$pkgname.install
source=(
  "https://mirrors.kernel.org/ubuntu/pool/universe/u/${_pkgname}/${_pkgname}_${_pkgver}-${_pkgrel}_amd64.deb"
  'udptunnel@.service'
  'udptunnel-wrapper'
)
sha256sums=(
  '99d4c88fe7c04c77ff9ef4578e57d37eef7a6cb4e44c4be76e8839be6bcec398'
  '178391a0624b0ffbb91950ff826ea82c5e67b5bf5e807f14589717594a67bcbf'
  'c76430b888115512255a62e3d922da5c18a4b509c4b1410c2ef8173e5c9bd03f'
)

prepare() {
  tar -xvf data.tar.zst
}

package() {
  install -d "${pkgdir}/etc/udptunnel"
  install -d "${pkgdir}/usr/bin"
  install -d "${pkgdir}/usr/share/doc/udptunnel"
  install -d "${pkgdir}/usr/share/man/man1"
  install -d "${pkgdir}/usr/lib/systemd/system"
  install -d "${pkgdir}/usr/lib/udptunnel"
  install -Dm755 "${srcdir}/usr/bin/"* "${pkgdir}/usr/bin/"
  install -Dm644 "${srcdir}/usr/share/doc/udptunnel/"* "${pkgdir}/usr/share/doc/udptunnel/"
  install -Dm644 "${srcdir}/usr/share/man/man1/"* "${pkgdir}/usr/share/man/man1/"
  install -Dm644 "${srcdir}/udptunnel@.service" "${pkgdir}/usr/lib/systemd/system/"
  install -Dm755 "${srcdir}/udptunnel-wrapper" "${pkgdir}/usr/lib/udptunnel/"
}
