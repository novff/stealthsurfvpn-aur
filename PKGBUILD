pkgname=stealthsurf-vpn
pkgver=1.0.17
pkgrel=1
arch=('x86_64')

# makepkg will use these instead of debtap's faulty 'gtk' mapping.
depends=('cairo' 'gdk-pixbuf2' 'gtk3' 'hicolor-icon-theme' 'libayatana-appindicator' 'libsoup3' 'webkit2gtk-4.1')

source=("https://cdn.stealthsurf.net/app/desktop/latest/StealthSurf-linux-amd64.deb")
sha256sums=('SKIP')

build() {
    cd "$srcdir"
    
    # Run debtap in quiet mode to translate the filesystem
    debtap -q app.deb
    
    # Rename the output to a predictable filename
    mv *.pkg.tar.zst stealthsurf-vpn.pkg.tar.zst
}

package() {
    bsdtar -xf "$srcdir/stealthsurf-vpn.pkg.tar.zst" -C "$pkgdir" --exclude='.PKGINFO'
}
