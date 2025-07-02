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
#        'curl'
#        'at-spi2-core'
#        'dbus'
#        'gtk3'
#        'glib2'
#        'webkit2gtk-4.1'
#        'hicolor-icon-theme'
#        'libsoup3'
#        'libsecret'
#        'libpwquality'
#        'libp11-kit'
#        'libx11'
#        'openssl'
#        'pam'
#        'pango'
#        'sqlite'
#        'systemd-libs'
#        'microsoft-identity-broker'
#        'zlib'
)
#install=$pkgname.install
source=("https://mirrors.kernel.org/ubuntu/pool/universe/u/${_pkgname}/${_pkgname}_${pkgver}-${pkgrel}_amd64.deb")
sha256sums=('99d4c88fe7c04c77ff9ef4578e57d37eef7a6cb4e44c4be76e8839be6bcec398')

prepare() {
    tar -xvf data.tar.xz
}

package() {
  install -d "$pkgdir"/usr/bin
  install -d "$pkgdir"/usr/share/doc/udptunnel
  install -d "$pkgdir"/usr/share/man/man1
  install -Dm755 "$srcdir"/usr/bin/* "$pkdir"/usr/bin/
  install -Dm644 "$srcdir"/usr/share/doc/udptunnel/* "$pkdir"/usr/share/doc/udptunnel/
  install -Dm644 "$srcdir"/usr/share/man/man1/* "$pkdir"/usr/share/man/man1/
}
