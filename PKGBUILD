pkgname='tiramisu-git'
_pkgname='tiramisu'
pkgver=r166.454c412
pkgrel=1
pkgdesc="Desktop notifications, the UNIX way"
makedepends=("vala")
arch=('x86_64')
url="https://github.com/Sweets/tiramisu"
license=('GPL')
depends=('glib2' 'glibc' 'zlib' 'libutil-linux' 'libffi' 'pcre')
makedepends=('git')
source=('tiramisu::git+https://github.com/Sweets/tiramisu.git')
md5sums=('SKIP')

pkgver() {
  cd "$_pkgname"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
	cd "$_pkgname"
	make
}

package() {
	cd "$_pkgname"
	install -Dm755 ./tiramisu "$pkgdir/usr/bin/tiramisu"
	install -Dm644 ./README.md -t "$pkgdir/usr/share/doc/$_pkgname/"
}
