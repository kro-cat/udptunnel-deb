# Maintainer: Kara <krocat1147@gmail.com>
pkgname=udptunnel-git
_pkgname=udptunnel
pkgver=1.1
pkgrel=10
pkgdesc="tunnel UDP packets over a TCP connection"
arch=('x86_64')
url="http://www1.cs.columbia.edu/~lennox/udptunnel/"
license=('Unknown')
provides=('udptunnel')
depends=(
  'libnsl'
  'glibc'
)
#install=$pkgname.install
source=("https://mirrors.kernel.org/ubuntu/pool/universe/u/${_pkgname}/${_pkgname}_${pkgver}-${pkgrel}_amd64.deb")
sha256sums=('99d4c88fe7c04c77ff9ef4578e57d37eef7a6cb4e44c4be76e8839be6bcec398')

prepare() {
  tar -xvf data.tar.zst
}

package() {
  install -d "$pkgdir"/usr/bin
  install -d "$pkgdir"/usr/share/doc/udptunnel
  install -d "$pkgdir"/usr/share/man/man1
  install -Dm755 "$srcdir"/usr/bin/* "$pkgdir"/usr/bin/
  install -Dm644 "$srcdir"/usr/share/doc/udptunnel/* "$pkgdir"/usr/share/doc/udptunnel/
  install -Dm644 "$srcdir"/usr/share/man/man1/* "$pkgdir"/usr/share/man/man1/
}
