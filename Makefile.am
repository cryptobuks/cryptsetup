EXTRA_DIST = COPYING.LGPL FAQ docs misc
SUBDIRS = po tests
TESTS =
CLEANFILES =
DISTCLEAN_TARGETS =

AM_CPPFLAGS = \
	-include config.h \
	-I$(top_srcdir)/lib \
        -DDATADIR=\""$(datadir)"\"              \
        -DLOCALEDIR=\""$(datadir)/locale"\"     \
        -DLIBDIR=\""$(libdir)"\"                \
        -DPREFIX=\""$(prefix)"\"                \
        -DSYSCONFDIR=\""$(sysconfdir)"\"        \
        -DVERSION=\""$(VERSION)"\"
AM_CFLAGS = -Wall
AM_LDFLAGS =

noinst_LTLIBRARIES =
sbin_PROGRAMS =
man8_MANS =

include man/Makemodule.am

include python/Makemodule.am

include scripts/Makemodule.am

include lib/crypto_backend/argon2/Makemodule.am
include lib/crypto_backend/Makemodule.am
include lib/Makemodule.am

include src/Makemodule.am

ACLOCAL_AMFLAGS = -I m4

DISTCHECK_CONFIGURE_FLAGS = 	\
	--enable-python		\
	--enable-cryptsetup-reencrypt

distclean-local:
	-find . -name \*~ -o -name \*.orig -o -name \*.rej | xargs rm -f
	rm -rf autom4te.cache

clean-local:
	-rm -rf docs/doxygen_api_docs
