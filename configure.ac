AC_PREREQ([2.69])

AC_INIT([ayatana-indicator-keyboard], [0.1.1])
AC_REVISION([0.1.0])

AC_CONFIG_SRCDIR([configure.ac])
AC_CONFIG_AUX_DIR([build-aux])
AC_CONFIG_MACRO_DIR([m4])

AM_INIT_AUTOMAKE([1.11 foreign serial-tests -Wall -Woverride -Wno-portability])
AM_SILENT_RULES([yes])

LT_INIT

AC_PROG_CC
AM_PROG_VALAC
AC_PROG_LIBTOOL
AC_PROG_INSTALL
PKG_PROG_PKG_CONFIG([0.26])

AC_ARG_WITH([dbus-service-dir], [AS_HELP_STRING([--with-dbus-service-dir=DIR], [D-Bus service directory [default=$datadir/dbus-1/services]])], [], [with_dbus_service_dir=$datadir/dbus-1/services])
AC_ARG_WITH([indicator-dir], [AS_HELP_STRING([--with-indicator-dir=DIR], [Indicator directory [default=$datadir/ayatana/indicators]])], [], [with_indicator_dir=$datadir/ayatana/indicators])

AM_PATH_PYTHON

AC_SUBST([DBUS_SERVICE_DIR], [$with_dbus_service_dir])
AC_SUBST([INDICATOR_DIR], [$with_indicator_dir])

GETTEXT_PACKAGE=ayatana-indicator-keyboard
AC_SUBST([GETTEXT_PACKAGE])
AC_DEFINE_UNQUOTED([GETTEXT_PACKAGE], ["$GETTEXT_PACKAGE"], [The prefix for our gettext translation domains.])
AM_GLIB_GNU_GETTEXT
IT_PROG_INTLTOOL

GLIB_GSETTINGS

PKG_CHECK_MODULES([GEE], [gee-1.0])
PKG_CHECK_MODULES([GIO], [gio-2.0])
PKG_CHECK_MODULES([GTK], [gtk+-3.0])
PKG_CHECK_MODULES([PANGOFT2], [pangoft2])
PKG_CHECK_MODULES([PANGOCAIRO], [pangocairo])
PKG_CHECK_MODULES([LIBXKLAVIER], [libxklavier])
PKG_CHECK_MODULES([LIBGNOMEKBD], [libgnomekbdui])
PKG_CHECK_MODULES([IBUS], [ibus-1.0])
PKG_CHECK_MODULES([FCITX_GCLIENT], [fcitx-gclient])
PKG_CHECK_MODULES([ACCOUNTSSERVICE], [accountsservice])
PKG_CHECK_MODULES([LIGHTDM], [liblightdm-gobject-1])

m4_include([m4/gcov.m4])
AC_TDD_GCOV
AM_CONDITIONAL([HAVE_GCOV], [test "x$ac_cv_check_gcov" = xyes])
AM_CONDITIONAL([HAVE_LCOV], [test "x$ac_cv_check_lcov" = xyes])
AM_CONDITIONAL([HAVE_GCOVR], [test "x$ac_cv_check_gcovr" = xyes])
AC_SUBST(COVERAGE_CFLAGS)
AC_SUBST(COVERAGE_CXXFLAGS)
AC_SUBST(COVERAGE_LDFLAGS)

AC_CONFIG_FILES([Makefile
                 data/Makefile
                 data/upstart/Makefile
                 src/Makefile
                 po/Makefile.in
                 tests/Makefile
                 tests/autopilot/Makefile
                 tests/config.vala
                 tests/services/ayatana-indicator-keyboard.service])
AC_CONFIG_FILES([tests/indicator-keyboard-test],
                [chmod +x tests/indicator-keyboard-test])

AC_OUTPUT
