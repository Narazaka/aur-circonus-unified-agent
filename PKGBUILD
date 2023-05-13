pkgname=circonus-unified-agent
_pkgver=0.2.12
pkgver="${_pkgver}"
pkgrel=1
pkgdesc="The Circonus Unified Agent, affectionately referred to as CUA [see-you-ey], is an agent for collecting metrics and writing them to the Circonus service."
arch=('x86_64')
url="https://github.com/circonus-labs/circonus-unified-agent"
license=('MIT')
depends=()
conflicts=()
backup=('opt/circonus/unified-agent/etc/circonus-unified-agent.conf')

source=("https://github.com/circonus-labs/circonus-unified-agent/releases/download/v${_pkgver}/circonus-unified-agent_${_pkgver}_linux_amd64.tar.gz"
 "cua.sysusers")

package() {
	install -Dm644 etc/conf.d/README.md              "${pkgdir}/opt/circonus/unified-agent/etc/conf.d/README.md"
	install -Dm644 etc/example-circonus-unified-agent.conf              "${pkgdir}/opt/circonus/unified-agent/etc/circonus-unified-agent.conf"
	install -Dm644 etc/logrotate.d/circonus-unified-agent              "${pkgdir}/etc/logrotate.d/circonus-unified-agent"
	install -Dm755 sbin/circonus-unified-agentd              "${pkgdir}/opt/circonus/unified-agent/sbin/circonus-unified-agentd"
	install -Dm644 service/circonus-unified-agent.linux.service          "${pkgdir}/usr/lib/systemd/system/${pkgname}.service"
	install -Dm644 cua.sysusers         "${pkgdir}/usr/lib/sysusers.d/cua.conf"
	install -D LICENSE                       "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}

sha256sums=('f5e46439bb80de75a8a361460ba2e88b719535e93c9580a780c69e9b89717726'
            'acf4befc49ff8a64031b76ee7417e59eb459451a6b356fa1bd6293e262e6cca0')
