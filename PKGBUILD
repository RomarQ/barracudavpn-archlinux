# Maintainer: Mike Achtelik <mike_achtelik at hotmail dot com>
# Contributor: David Birks <david@tellus.space>
# Contributor: Michele Cereda <cereda.michele@gmail.com>
# Contributor: JokerYu <dayushinn@gmail.com>
# Contributor: Olivier Bilodeau <obilodeau@gosecure.ca>

pkgname="barracudavpn"
pkgver="5.0.2.7"
pkgrel="1"
pkgdesc="Barracuda VPN Client for Linux"
arch=("i386" "x86_64")
install="${pkgname}.install"

url="https://campus.barracuda.com/product/networkaccessclient"
license=("custom:FortiClientSSLVPN")

depends=(
	"sh"
  "xterm"
)

source=(
  "${pkgname}_32"
  "${pkgname}_64"
	"${pkgname}_32.desktop"
  "${pkgname}_64.desktop"
	"${pkgname}.png"
)
sha256sums=('bd521ef41083b074d50e466d1e5b3a1550d88ef6a87c1d6826dfd8408d0cd1c5'
            '6a6f4459d1b7c06266a7f8748aeed6059522e6b0646b0b0d7393c1da970b3322'
            'b815d782fa4a3b70493abc875678251a3c8f8411cf1f00ef60c63fcf9da75e7d'
            '1225def0b5dac36dc4709b8f081d911a496aa2e436fe32edfb3ea7c4f0f0e441'
            '9a1494e98eaf46783eccce2bd1b537cf5ae158e5c9f55322e7b67da4dc1fd37a')

if   [ "$CARCH" = "i386"   ]; 
then 

  bin_location="usr/local/bin"
  bin_file="barracudavpn_32"

elif [ "$CARCH" = "x86_64" ];
then 

  bin_location="usr/bin"
  bin_file="barracudavpn_64"

fi
options=( !strip )

package() {
	msg "Creating folders..."
	mkdir -p ${pkgdir}/opt/${pkgname}/icons
  mkdir -p ${pkgdir}/usr/share/applications
	mkdir -p ${pkgdir}/${bin_location}

	msg "Installing files..."
  install -Dm 4755 ${srcdir}/${bin_file} ${pkgdir}/${bin_location}/${pkgname}
	install -Dm 4755 ${srcdir}/${pkgname}.png ${pkgdir}/opt/${pkgname}/icons/
	install -Dm 4755 ${srcdir}/${bin_file}.desktop ${pkgdir}/usr/share/applications/${pkgname}.desktop
}
