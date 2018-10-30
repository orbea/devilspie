# Initial blurb
AC_PREREQ(2.52)
AC_INIT([devilspie],[0.23],[http://www.burtonini.com/])
AC_CONFIG_SRCDIR(src/devilspie.c)
AM_INIT_AUTOMAKE([1.11 no-dist-gzip dist-xz])
AM_SILENT_RULES([yes])
AC_CONFIG_HEADERS([src/config.h])

# Do the gettext/i18n stuff
GETTEXT_PACKAGE=devilspie
AC_DEFINE_UNQUOTED(GETTEXT_PACKAGE, "$GETTEXT_PACKAGE", [The name of the gettext package.])
AC_SUBST(GETTEXT_PACKAGE)

AC_PROG_CC
AM_PROG_CC_STDC

AC_PROG_INTLTOOL([0.40.0])
AM_GLIB_GNU_GETTEXT

# Check that we actually have the libraries required to build
PKG_CHECK_MODULES(WNCK,
        glib-2.0 >= 2.10.0
        gdk-3.0
        gdk-x11-3.0
        x11
        libwnck-3.0 >= 3.0.0)
AC_SUBST(WNCK_CFLAGS)
AC_SUBST(WNCK_LIBS)

# Check for the POSIX regexpr functions and headers
AC_CHECK_FUNCS([regcomp regexec regfree])
AC_CHECK_HEADERS([sys/types.h regex.h])

AC_OUTPUT([
devilspie.spec
Makefile
src/Makefile
po/Makefile.in
tests/Makefile
])
