# Maintainer: Stijn Seghers <stijnseghers at gmail dot com>

pkgname=xmobar
pkgver=0.46
pkgrel=1
pkgdesc='Minimalistic Text Based Status Bar'
url='https://codeberg.org/xmobar/xmobar'
license=('BSD')
arch=('x86_64')
depends=(
    'pango'
    'libx11'
    'libxrandr'
    'libxss'
    'libxinerama'
    'alsa-lib'
)
makedepends=('git' 'stack')
conflicts=('xmobar')
provides=('xmobar')


build() {
    stack install "${pkgname}-${pkgver}" \
        --local-bin-path . \
        --flag xmobar:-all_extensions \
        --flag xmobar:-with_xrender \
        --flag xmobar:with_nl80211 \
        --flag xmobar:with_alsa \
        --flag xmobar:with_threaded \
        --flag xmobar:-with_weather
}

package() {
    install -Dm 755 xmobar -t "${pkgdir}/usr/bin/"
}
