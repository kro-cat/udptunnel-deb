# Maintainer: Kara <krocat1147@gmail.com>
pkgname=udptunnel-deb
_pkgname=udptunnel
pkgver=1.1
pkgrel=10
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
  "https://mirrors.kernel.org/ubuntu/pool/universe/u/${_pkgname}/${_pkgname}_${pkgver}-${pkgrel}_amd64.deb"
  'udptunnel@.service'
  'udptunnel-wrapper'
)
sha256sums=(
  '99d4c88fe7c04c77ff9ef4578e57d37eef7a6cb4e44c4be76e8839be6bcec398'
  '675eb901df283c774c44a0b6d4910a1f007e80444e5341acb3292b64c0cd9fb6'
  'c5045101efe1e3d193bd2d2d8828a5385e4137ce72bca744016a5f9eac394dee'
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
