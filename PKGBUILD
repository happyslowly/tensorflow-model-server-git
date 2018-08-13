pkgname=tensorflow-model-server-git
pkgver=r1.10
pkgrel=1
pkgdesc="A flexible, high-performance serving system for machine learning models"
arch=("x86_64")
url="https://tensorflow.org/serving"
license=('apache2')
source=("git+https://github.com/tensorflow/serving.git")
makedepends=(git bazel gcc7)
md5sums=('SKIP')
build() {
    cd $srcdir/serving
    git checkout $pkgver
    bazel build -c opt tensorflow_serving/model_servers:tensorflow_model_server
}
package() {
    install -Dm755 $srcdir/serving/bazel-bin/tensorflow_serving/model_servers/tensorflow_model_server ${pkgdir}/usr/bin/tensorflow_model_server
}
