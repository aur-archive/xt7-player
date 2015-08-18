# Maintainer : Antonio Orefice <xt7player@gmail.com>

pkgname=xt7-player
_realname=xt7-player
pkgver=3.5.4
pkgrel=1
pkgdesc="Aims to be an 'almost complete' but usable mplayer gui"
arch=('any')
url="http://xt7-player.sourceforge.net/xt7forum/"
license=('custom')

makedepends=('gambas3-devel')

depends=('gambas3-gb-image>=3.3.0' 
    'gambas3-runtime>=3.3.0'
    'gambas3-gb-form>=3.3.0'
	'gambas3-gb-qt4>=3.3.0'
	'gambas3-gb-dbus>=3.3.0' 
	'gambas3-gb-desktop>=3.3.0' 
	'gambas3-gb-settings>=3.3.0' 
	'gambas3-gb-form-mdi>=3.3.0' 
	'gambas3-gb-form-dialog>=3.3.0' 
	'gambas3-gb-net>=3.3.0' 
	'gambas3-gb-net-curl>=3.3.0' 
	'gambas3-gb-qt4-ext>=3.3.0' 
	'gambas3-gb-web>=3.3.0' 
	'gambas3-gb-libxml>=3.3.0'
	'gambas3-gb-form-stock>=3.3.0' 
	'gambas3-gb-compress'
	'gambas3-gb-signal'
	'gambas3-gb-desktop-x11'
	'mplayer'
	'taglib'
	'youtube-dl>=2014.03.21'
	'wget')


makedepends=('gambas3-devel')
optdepends=('python2: for Opensubtitles.org integration' 
			'ladspa: more audio plugins'
			'linuxtv-dvb-apps: for DVB support' 
			'dvbsnoop: DVBT EPG' 
			'xdg-utils: for desktop integration' 
			'xbindkeys: for global hotkeys support' 
			'aria2: for youtube segmented downloads')

source=(http://wpage.unina.it/aorefice/xt7player_dist/xt7-$pkgver/autotools/xt7-player-$pkgver.tar.gz 'license.txt' \
        'xt7-player.desktop')

md5sums=('1b5f2f44b65eb57e1e2797ac97cb11b0'
         'b6f1380e33b47d0ed95c7ba1b3f4ec73'
         'edf3ec8df54a4f1bd6c25114073e15b5')

build() {
  cd ${srcdir}/${_realname}-${pkgver}
  ./configure --prefix=/usr

  make || return 1
}

package() {
  cd ${srcdir}/${_realname}-${pkgver}/${_realname}
  install -d ${pkgdir}/usr/bin
  install -m755 xt7-player.gambas ${pkgdir}/usr/bin/xt7-player
  install -D xt7-player.png \
    ${pkgdir}/usr/share/pixmaps/xt7-player.png
  install -D ../../xt7-player.desktop \
    ${pkgdir}/usr/share/applications/xt7-player.desktop
  install -Dm644 ${srcdir}/license.txt ${pkgdir}/usr/share/licenses/xt7-player/license.txt
}
