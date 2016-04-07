pkgname=stremio
pkgver=3.5.7
pkgrel=1
pkgdesc="Watch instantly All The Video Content You Enjoy in One Place"
arch=('x86_64')
url="https://strem.io"
depends=('gconf' 'ffmpeg')
license=('custom')
install=stremio.install
source=("https://strem.io/Stremio${pkgver}.linux.tar.gz"
        "stremio-32x32.png"
        "stremio-96x96.png"
        "stremio.desktop")
md5sums=('15f2bc9b1099af41920bec49b8bad88f'
         '45fb8ede7938c41df4dd52bded7aa018'
         'e3b38592637449733618d73b45293b09'
         '1824da5ef113f63f2e414510fb8c43e3')

prepare() {
  sed -i "s#\$(dirname \$0)#/usr/share/stremio#" Stremio.sh
}

package() {
  install -dm755 "$pkgdir/usr/share/stremio"
  cp -pr {locales,resources,WCjs} "$pkgdir/usr/share/stremio/"
  install -Dm755 Stremio-runtime "$pkgdir/usr/share/stremio/"
  install -Dm755 Stremio.sh "$pkgdir/usr/bin/stremio"
  install -Dm644 {content_shell.pak,icudtl.dat,libgcrypt.so.11,libnode.so,libnotify.so.4,natives_blob.bin,snapshot_blob.bin,version} "$pkgdir/usr/share/stremio/"
  install -Dm644 stremio.desktop "$pkgdir/usr/share/applications/stremio.desktop"
  install -Dm644 stremio-32x32.png "$pkgdir/usr/share/icons/hicolor/32x32/apps/stremio.png"
  install -Dm644 stremio-96x96.png "$pkgdir/usr/share/icons/hicolor/96x96/apps/stremio.png"
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/stremio/LICENSE"
}


