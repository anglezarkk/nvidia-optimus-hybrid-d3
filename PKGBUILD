# Maintainer: Anglezarkk <anglexarkk.git at tarellia dot net>

pkgname=nvidia-optimus-hybrid-d3
pkgver=0.1
pkgrel=1
pkgdesc="Enable PRIME offloading while retaining battery life by putting the dGPU in D3cold mode."
arch=("any")
url="https://github.com/anglezarkk/nvidia-optimus-hybrid-d3"
license=('MIT')
depends=('nvidia' 'tlp' 'git')
source=("git://github.com/anglezarkk/nvidia-optimus-hybrid-d3.git")
sha1sums=('SKIP')

package() {
    install=".INSTALL"
    cd "${srcdir}"
    
    install -Dm 644 etc/modprobe.d/anvidia.conf "$pkgdir/etc/modprobe.d/anvidia.conf"
    install -Dm 644 etc/modprobe.d/disable-ipmi.conf "$pkgdir/etc/modprobe.d/disable-ipmi.conf"
    install -Dm 644 etc/modprobe.d/disable-nvidia.conf "$pkgdir/etc/modprobe.d/disable-nvidia.conf"

    install -Dm 644 etc/tempfiles.d/nvidia_pm.conf "$pkgdir/etc/tempfiles.d/nvidia_pm.conf"

    install -Dm 644 etc/systemd/system/disable-nvidia-on-shutdown.service "$pkgdir/etc/systemd/system/disable-nvidia-on-shutdown.service"

    install -Dm 644 etc/X11/xorg.conf.d/01-noautogpu.conf "$pkgdir/etc/X11/xorg.conf.d/01-noautogpu.conf"
    install -Dm 644 etc/X11/xorg.conf.d/20-intel.conf "$pkgdir/etc/X11/xorg.conf.d/20-intel.conf"

    install -Dm 755 usr/bin/disablegpu "$pkgdir/usr/bin/disablegpu"
    install -Dm 755 usr/bin/enablegpu "$pkgdir/usr/bin/enablegpu"
}