# Maintainer: Alexander F. Rødseth <xyproto@archlinux.org>
# Maintainer: Daniel Bershatsky <archlinux-ai@daskol.xyz>

pkgname='python-diffusers'
_pkgname=${pkgname#python-}
pkgver=0.20.1
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
sha256sums=('91901e4ab8e6bde76a33703b5a8c3998507639e1d48d7e65d8e9f53a192c3b24')

build() {
    python -m build -nw $_pkgname-$pkgver
}

package() {
    python -m installer \
        --compile-bytecode 1 \
        --destdir $pkgdir \
        $_pkgname-$pkgver/dist/$_pkgname-$pkgver-*-*.whl
}
