# Maintainer: Ashin Antony <ashinant15@gmail.com>

pkgname=slstatus-ashin-git
pkgver=2.1
pkgrel=1
pkgdesc='A suckless status with cpu,ram,updates,volume,wlan and date widgets.'
arch=(x86_64) 
url='https://github.com/ashincoder/slstatus-ashin.git'
license=('custom:ISC')
depends=(libx11)
optdepends=()
makedepends=(git)
checkdepends=()
provides=(slstatus)
conflicts=(slstatus)
replaces=()
backup=()
options=()
source=("git+$url")
noextract=()
md5sums=('SKIP')
validpgpkeys=()

pkgver() {
  cd slstatus-ashin
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  cd slstatus-ashin
  make PREFIX=/usr 
}

package() {
  cd slstatus-ashin  
  mkdir -p ${pkgdir}/opt/${pkgname}
  cp -rf * ${pkgdir}/opt/${pkgname}
  make PREFIX=/usr DESTDIR="${pkgdir}" install
  install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
  install -Dm644 README "${pkgdir}/usr/share/doc/${pkgname}/README.md"
}

