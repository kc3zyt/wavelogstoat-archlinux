pkgname_=WaveLogStoat
pkgname=wavelogstoat
pkgver=0.0.4
pkgrel=2
pkgdesc='Go PKGBUILD Example'
arch=('x86_64')
url="https://github.com/int2001/$pkgname_"
license=('GPL')
makedepends=('go')
source=("$url/archive/refs/tags/v$pkgver.tar.gz")
sha256sums=('46a62da5234afd14cbea265131c810c79bcf76f8b9043d2db29726c40a41e0c9')

prepare(){
	cd "$pkgname_-$pkgver"
#	mkdir -p build/
}

build() {
	cd "$pkgname_-$pkgver"
	export CGO_CPPFLAGS="${CPPFLAGS}"
	export CGO_CFLAGS="${CFLAGS}"
	export CGO_CXXFLAGS="${CXXFLAGS}"
	#export CGO_LDeeFLAGS="${LDFLAGS}"
	#export GOFLAGS="-buildmode=pie -trimpath -ldflags=-linkmode=external -mod=readonly -modcacherw"
	go mod tidy
	go build -buildvcs=false  -o "$pkgname"
}

check() {
	cd "$pkgname_-$pkgver"
	go test ./...
}

package() {
	cd "$pkgname_-$pkgver"
	install -Dm755 "$pkgname" "$pkgdir"/usr/bin/$pkgname
}
