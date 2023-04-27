pkgname=encrypt-timeout-hook
pkgver=1.0.0
pkgrel=1
pkgdesc="Custom encrypt hook with shutdown timeout for Arch Linux"
arch=('any')
url="https://github.com/yourusername/custom-encrypt-hook"
license=('GPL')
depends=('cryptsetup')

package() {
  mkdir -p "${pkgdir}/etc/initcpio/hooks"
  mkdir -p "${pkgdir}/etc/initcpio/install"

  install -m755 encrypt-timeout "${pkgdir}/etc/initcpio/hooks/encrypt-timeout"
  install -m755 encrypt-timeout-install "${pkgdir}/etc/initcpio/install/encrypt-timeout"
}
