dnl
dnl Copyright (c) 2008 Mikhail Gusarov <dottedmag@dottedmag.net>
dnl
dnl BSD-3
dnl

AC_PREREQ([2.69])
AC_INIT([x2x],[1.30-rc1],[http://x2x.dottedmag.net/newticket],[x2x],[http://x2x.dottedmag.net])
AM_INIT_AUTOMAKE([foreign dist-bzip2])
AC_CONFIG_SRCDIR([x2x.c])

# config.h is unused but generating it avoids compiler invocation clutter.
AC_CONFIG_HEADERS([config.h])

AC_PROG_CC
AC_PROG_INSTALL

AX_CFLAGS_WARN_ALL

## This PKG_CHECK_MODULES can be replaced by the following three
## AC_SEARCH_LIBSs and the non-Cygwin setting of AM_LDFLAGS and
## AM_CFLAGS in Makefile.am removed.
PKG_CHECK_MODULES(X11, xext xtst x11)
# AC_SEARCH_LIBS([XOpenDisplay], [X11 x11])
# AC_SEARCH_LIBS([XextFindDisplay], [Xext xext])
# AC_SEARCH_LIBS([XTestFakeKeyEvent], [Xtst xtst])

CFLAGS="${X11_CFLAGS} ${CFLAGS}"
LIBS="${X11_LIBS} ${LIBS}"

AC_ARG_ENABLE([win32],
    AS_HELP_STRING(
        [--enable-win32],
        [enable Win32 support (-fromwin option). Disabled by default]))

AM_CONDITIONAL(WIN32, [test x$enable_win32 = xyes])

AC_CONFIG_FILES([Makefile])
AC_OUTPUT
