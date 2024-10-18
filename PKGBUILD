# Maintainer: Gregory Velichko  <re7gog@gmail.com>
# Contributor: Mikhail Velichko  <efklid@gmail.com>
# I don't know Mikhail

_pkgname=browser-beta
pkgname=yandex-browser-beta
pkgver=24.7.6.1043
_pkgver=24.7.6.1043-1
pkgrel=1
#epoch=1

pkgdesc="The web browser from Yandex, Beta version.
 Yandex Browser is a browser that combines a minimal design with sophisticated technology to make the web faster, safer, and easier."
arch=("x86_64")
url='https://browser.yandex.com/beta/'
license=("custom:yandex-browser")
categories=("network")
provides=(yandex-browser-beta)
conflicts=('yandex-browser-beta' 'yandex-browser' 'yandex-browser-stable')

depends=( "binutils" "ttf-liberation" "jq" "alsa-lib" "at-spi2-atk" "libcups" "curl" "dbus" "libdrm" "gdbm" "gtk4" "nspr" "nss" "pango"
"wayland" "libxcomposite" "libxdamage" "libxkbcommon" "libxkbfile" "libxrandr" "squashfs-tools" "wget" "xdg-utils" "harfbuzz-icu")
optdepends=(
    "speech-dispatcher"
    "vulkan-driver"
    "vulkan-icd-loader"
    "ttf-font"
    "gstreamer-meta"
    "cryptopro-csp-k1"
)

source=("${pkgname}-${_pkgver}.deb::https://repo.yandex.ru/yandex-browser/deb/pool/main/y/yandex-${_pkgname}/yandex-${_pkgname}_${_pkgver}_amd64.deb")
sha256sums=("24c27066556be59209320bc3a4032a0d3aa637f404d039637bf3243dc0bd174f")
install=yandex-browser-beta.install

prepare() {
    tar -xf data.tar.xz
}

package() {
    cp -dr --no-preserve=ownership opt usr "${pkgdir}"/
# The beta version uses the "browser-beta" folder in /opt/yandex. ${_pkgname} cannot be used in this section for the beta branch 
#    install -D -m0644 "${pkgdir}"/opt/yandex/browser-beta/product_logo_128.png "${pkgdir}"/usr/share/pixmaps/${pkgname}.png
    chmod 4755 "${pkgdir}"/opt/yandex/browser-beta/yandex_browser-sandbox
}
