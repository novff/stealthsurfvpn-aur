pkgname=stealthsurf-vpn
pkgver=1.0.17
pkgrel=1
pkgdesc="StealthSurf VPN Desktop Client"
arch=('x86_64')
url="https://stealthsurf.net"

depends=('cairo' 'gdk-pixbuf2' 'gtk3' 'hicolor-icon-theme' 'libayatana-appindicator' 'libsoup3' 'webkit2gtk-4.1') 
source=("stealthsurf.deb::https://cdn.stealthsurf.net/app/desktop/latest/StealthSurf-linux-amd64.deb")
sha256sums=('SKIP')

package() {
    # 1. Extract the .deb file (bsdtar natively supports 'ar' archives)
    bsdtar -xf "${srcdir}/stealthsurf.deb" -C "${srcdir}"
    
    # 2. Extract the actual payload (data.tar.zst, data.tar.xz, or data.tar.gz) into the package directory
    bsdtar -xf "${srcdir}"/data.tar.* -C "${pkgdir}"
}
