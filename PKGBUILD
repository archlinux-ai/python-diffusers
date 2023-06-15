# Maintainer: Alexander F. Rødseth <xyproto@archlinux.org>
# Maintainer: Daniel Bershatsky <archlinux-ai@daskol.xyz>

pkgname='python-diffusers'
_pkgname=${pkgname#python-}
pkgver=0.17.1
pkgrel=1
pkgdesc='Pretrained diffusion models'
arch=('x86_64')
url='https://github.com/huggingface/diffusers'
license=('Apache')
depends=(
    'python-filelock'
    'python-huggingface-hub'
    'python-importlib-metadata'
    'python-numpy'
    'python-pillow'
    'python-regex'
    'python-requests'
)
makedepends=('python-build' 'python-installer' 'python-setuptools' 'python-wheel')
source=("$pkgname-$pkgver::https://github.com/huggingface/$_pkgname/archive/refs/tags/v$pkgver.tar.gz")
sha256sums=('ad2f45f25695afa75ce63735594f42b120f8218e53989b4a3e0c6bec37f10e27')

build() {
    cd $_pkgname-$pkgver
    python -m build -nw
}

package() {
    python -m installer \
        --compile-bytecode 1 \
        --destdir $pkgdir \
        $_pkgname-$pkgver/dist/$_pkgname-$pkgver-*-*.whl
}
