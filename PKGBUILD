# Maintainer: Alexander F. Rødseth <xyproto@archlinux.org>
# Maintainer: Daniel Bershatsky <archlinux-ai@daskol.xyz>

pkgname='python-diffusers'
_pkgname=${pkgname#python-}
pkgver=0.19.3
pkgrel=1
pkgdesc='State-of-the-art diffusion models for image and audio generation in PyTorch'
arch=('any')
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
    'python-safetensors'
)
makedepends=('python-build' 'python-installer' 'python-setuptools' 'python-wheel')
source=("$pkgname-$pkgver::https://github.com/huggingface/$_pkgname/archive/refs/tags/v$pkgver.tar.gz")
sha256sums=('559a168a2157a12be0d5df8538c6a235d23a8db17d53b5201381b48b6b6d29c7')

build() {
    python -m build -nw $_pkgname-$pkgver
}

package() {
    python -m installer \
        --compile-bytecode 1 \
        --destdir $pkgdir \
        $_pkgname-$pkgver/dist/$_pkgname-$pkgver-*-*.whl
}
