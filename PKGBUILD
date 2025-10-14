# Maintainer: Ethan <yeah_yaojiu@163.com>

pkgname=piliplus-bin
pkgver=1.1.4.10
_version=1.1.4+4215
pkgrel=1
url="https://github.com/bggRGjQaUbCoE/PiliPlus"
pkgdesc="A Bilibili third-party client built with Flutter. | 使用Flutter开发的BiliBili第三方客户端"
arch=('x86_64')
license=('GPL3.0')
depends=('gtk3' 'mpv' 'libayatana-appindicator')
source=("${url}/releases/download/${pkgver}/PiliPlus_linux_${_version}_amd64.tar.gz")
options=(!debug)

sha256sums=('47af8b42b174cf171e64abe74f1050cdd5bde87287793505e8d5c91e7c24697c')

package() {

  install -d "$pkgdir/opt/$pkgname"
  
  cp "$srcdir/piliplus" "$pkgdir/opt/$pkgname/"
  cp -r "$srcdir/lib" "$pkgdir/opt/$pkgname/"
  cp -r "$srcdir/data" "$pkgdir/opt/$pkgname/"


 install -Dm644 "$srcdir/data/flutter_assets/assets/images/logo/logo.png" \
    "$pkgdir/usr/share/icons/hicolor/256x256/apps/$pkgname.png"

  install -Dm644 /dev/stdin "$pkgdir/usr/share/applications/$pkgname.desktop" <<EOF
[Desktop Entry]
Name=PiliPlus
Comment=A Bilibili third-party client built with Flutter.
Exec=piliplus
Icon=$pkgname
Terminal=false
Type=Application
Categories=Utility;
EOF

  install -d "$pkgdir/usr/bin"
  ln -s "/opt/$pkgname/piliplus" "$pkgdir/usr/bin/piliplus"
}
