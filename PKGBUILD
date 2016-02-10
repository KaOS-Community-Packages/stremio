pkgname=stremio
pkgver=3.5.1
pkgrel=1
pkgdesc="Watch instantly All The Video Content You Enjoy in One Place"
arch=('x86_64')
url="https://strem.io"
depends=('gconf' 'ffmpeg')
license=('custom')
install=stremio.install
source=("https://strem.io/Stremio${pkgver}.linux.tar.gz"
        "favicon-32x32.png::http://i.imgur.com/8rYxdKN.png"
        "https://strem.io/favicon-96x96.png"
        "stremio.desktop")
md5sums=('abcd6ff712b279ad8b51b8148a85e1f2'
         '45fb8ede7938c41df4dd52bded7aa018'
         'e3b38592637449733618d73b45293b09'
         '1824da5ef113f63f2e414510fb8c43e3')

prepare() {
  sed -i "s#\$(dirname \$0)#/usr/share/stremio#" Stremio.sh
}

package() {
  install -Dm644 stremio.desktop "$pkgdir/usr/share/applications/stremio.desktop"
  install -Dm644 favicon-32x32.png "$pkgdir/usr/share/icons/hicolor/32x32/apps/stremio.png"
  install -Dm644 favicon-96x96.png "$pkgdir/usr/share/icons/hicolor/96x96/apps/stremio.png"

  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/stremio/LICENSE"
  install -Dm755 Stremio.sh "$pkgdir/usr/bin/stremio"

  install -dm755 "$pkgdir/usr/share/stremio"

  install -Dm644 content_shell.pak "$pkgdir/usr/share/stremio/"
  install -Dm644 icudtl.dat "$pkgdir/usr/share/stremio/"
  install -Dm644 libgcrypt.so.11 "$pkgdir/usr/share/stremio/"
  install -Dm644 libnode.so "$pkgdir/usr/share/stremio/"
  install -Dm644 libnotify.so.4 "$pkgdir/usr/share/stremio/"
  install -Dm644 natives_blob.bin "$pkgdir/usr/share/stremio/"
  install -Dm644 snapshot_blob.bin "$pkgdir/usr/share/stremio/"
  install -Dm755 Stremio-runtime "$pkgdir/usr/share/stremio/"
  install -Dm644 version "$pkgdir/usr/share/stremio/"

  cp -pr locales "$pkgdir/usr/share/stremio/"
  cp -pr resources "$pkgdir/usr/share/stremio/"
  cp -pr WCjs "$pkgdir/usr/share/stremio/"
}


