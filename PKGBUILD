pkgname="virtual-drive"
pkgver="0.2.0"
pkgrel=1
pkgdesc="A command line utility managing virtual encrypted drives."
arch=("any")
depends=("bash" "grep" "util-linux" "cryptsetup" "e2fsprogs")
license=('GPL-2.0')

makedepends=("git")
source=("https://github.com/GaryBlackbourne/${pkgname}/archive/${pkgver}.tar.gz")
sha256sums=("856b3e18408a5694f6f9b0072ae6ffcafc2c64a84f73e230cbeea5391ff54558")

package() {

    launcher=$pkgdir/usr/bin/virtual-drive
    install_dir=$pkgdir/usr/lib/virtual-drive

    cd $pkgname-$pkgver

    mkdir -p $pkgdir/usr/lib/virtual-drive
    cp virtual-drive $install_dir
    cp -r functions $install_dir

    mkdir -p $(dirname $launcher)
    echo '#!/usr/bin/bash' > $launcher
    echo 'exec /usr/lib/virtual-drive/virtual-drive "$@"' >> $launcher

    mkdir -p $pkgdir/usr/share/fish/vendor_completions.d
    cp shell-completions/virtual-drive.fish \
       $pkgdir/usr/share/fish/vendor_completions.d/

    chmod +x $launcher
}
