pkgname=stealthsurf-vpn
pkgver=1.0.17
pkgrel=1
arch=('x86_64')

depends=('cairo' 'gdk-pixbuf2' 'gtk3' 'hicolor-icon-theme' 'libayatana-appindicator' 'libsoup3' 'webkit2gtk-4.1') 
makedepends=('pacman-contrib' 'git' 'debtap' 'wget')
#source=("stealthsurf.deb::https://cdn.stealthsurf.net/app/desktop/latest/StealthSurf-linux-amd64.deb")
sha256sums=('SKIP')

build() {
    wget -O "stealthsurf.deb" https://cdn.stealthsurf.net/app/desktop/latest/StealthSurf-linux-amd64.deb
    #run debtap postinstall req.
    sudo debtap -u
    #run debtap to convert package.
    debtap -Q "stealthsurf.deb"
    #rename into proper temporary package
    mv *.pkg.tar.zst "temp.pkg.tar.zst"
}

package() {
    bsdtar -xf "temp.pkg.tar.zst" \
        -C "$pkgdir" \
        --exclude='.PKGINFO' \
        --exclude='.INSTALL'
}
