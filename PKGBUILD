pkgname=stealthsurf-vpn
pkgver=1.0.17
pkgrel=1
arch=('x86_64')

depends=('cairo' 'gdk-pixbuf2' 'gtk3' 'hicolor-icon-theme' 'libayatana-appindicator' 'libsoup3' 'webkit2gtk-4.1')

source=("stealthsurf.deb::https://cdn.stealthsurf.net/app/desktop/latest/StealthSurf-linux-amd64.deb")
sha256sums=('SKIP')

build() {
    cd "$srcdir"
    debtap -q stealthsurf.deb
    mv *.pkg.tar.zst "${pkgname}-${pkgver}-${pkgrel}-x86_64.pkg.tar.zst"
}

package() {
    cd "$srcdir"
    bsdtar -xf "${pkgname}-${pkgver}-${pkgrel}-x86_64.pkg.tar.zst" \
        -C "$pkgdir" \
        --exclude='.PKGINFO' \
        --exclude='.INSTALL'
}
