pkgname="virtual-drive"
pkgver="0.1.0"
pkgrel=1
pkgdesc="A command line utility managing virtual encrypted drives."
arch=("any")
depends=("bash" "grep" "util-linux" "cryptsetup" "e2fsprogs")
license=('GPL-2.0')

makedepends=("git")
source=("https://github.com/GaryBlackbourne/${pkgname}/archive/${pkgver}.tar.gz")
sha256sums=("286b381b48416e21abf797d0b7ed8c1e9eb3d8ff250a5060902aa9c249a9797f")

package() {

    launcher=$pkgdir/usr/bin/virtual-drive
    install_dir=$pkgdir/usr/lib/virtual-drive

    cd $pkgname-$pkgver

    mkdir -p $pkgdir/usr/lib/virtual-drive
    cp virtual-drive $install_dir
    cp -r functions $install_dir

    echo '#!/usr/bin/bash' > $launcher
    echo 'exec /usr/lib/virtual-drive "$@"' >> $launcher

    chmod +x $launcher
}
