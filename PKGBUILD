pkgname=('glrnvim')
_pkgname="glrnvim"
pkgver=0.1.0
pkgrel=1
arch=('x86_64' 'i686')
url='https://github.com/beeender/glrnvim'
license=('GPL3')
makedepends=('rust' 'cargo' 'git')
source=('git+https://github.com/beeender/glrnvim.git#branch=master')
sha256sums=('SKIP')

package_glrnvim() {
	pkgdesc="A GPU-accelerated neovim GUI."
	depends=('alacritty' 'neovim')
	provides=('glrnvim')

	cd "$srcdir/$_pkgname"
	env CARGO_INCREMENTAL=0 cargo build --release

	install -D -m755 "$srcdir/$_pkgname/target/release/glrnvim" "$pkgdir/usr/bin/glrnvim"
    install -Dm644 $srcdir/$_pkgname/glrnvim.desktop "$pkgdir/usr/share/applications/glrnvim.desktop"
    install -Dm644 $srcdir/$_pkgname/glrnvim.svg "$pkgdir/usr/share/icons/glrnvim.svg"
}