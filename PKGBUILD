pkgname='perl-template-plugin-number-format'
pkgver='1.02'
pkgrel='1'
pkgdesc="Template::Plugin::Number::Format - Plugin/filter interface to Number::Format"
arch=('any')
license=('PerlArtistic' 'GPL')
options=('!emptydirs')
depends=('perl' 'perl-number-format' 'perl-template-toolkit')
makedepends=()
url='http://search.cpan.org/perldoc?Template%3A%3APlugin%3A%3ANumber%3A%3AFormat'
source=("http://search.cpan.org/CPAN/authors/id/D/DA/DARREN/Template-Plugin-Number-Format-$pkgver.tar.gz")
md5sums=('6ccfbc9db84fc86ae64aae9973f037cf')

build() {
  ( export PERL_MM_USE_DEFAULT=1 PERL5LIB=""                 \
      PERL_AUTOINSTALL=--skipdeps                            \
      PERL_MM_OPT="INSTALLDIRS=vendor DESTDIR='$pkgdir'"     \
      PERL_MB_OPT="--installdirs vendor --destdir '$pkgdir'" \
      MODULEBUILDRC=/dev/null

    cd "${srcdir}/Template-Plugin-Number-Format-$pkgver" 
    /usr/bin/perl Makefile.PL
    make
  )
}

check() {
  cd "${srcdir}/Template-Plugin-Number-Format-$pkgver"
  ( export PERL_MM_USE_DEFAULT=1 PERL5LIB=""
    make test
  )
}

package() {
  cd "${srcdir}/Template-Plugin-Number-Format-$pkgver"
  make install
  find "$pkgdir" -name .packlist -o -name perllocal.pod -delete
}
