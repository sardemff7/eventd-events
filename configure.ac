m4_define([eventd_events_version], [0])
m4_define([eventd_homepage], [http://www.eventd.org])
AC_PREREQ([2.65])
AC_INIT([eventd-events],eventd_events_version,[],[],eventd_homepage)

AC_CONFIG_MACRO_DIR([m4])
AC_CONFIG_AUX_DIR([.aux])

AM_INIT_AUTOMAKE([1.14 foreign subdir-objects parallel-tests dist-xz no-dist-gzip tar-ustar])
AM_SILENT_RULES([yes])

AC_PROG_MKDIR_P
AC_PROG_INSTALL
PKG_PROG_PKG_CONFIG

GETTEXT_PACKAGE=${PACKAGE_NAME}
AC_DEFINE_UNQUOTED([GETTEXT_PACKAGE], ["${GETTEXT_PACKAGE}"], [Gettext Package])
AC_SUBST([GETTEXT_PACKAGE])
IT_PROG_INTLTOOL([0.40.0])

AC_CANONICAL_HOST
case "${host_os}" in
    mingw*)
        pkg_config_extra_args="--dont-define-prefix"
    ;;
    *)
        pkg_config_extra_args=
    ;;
esac

eventd_min_version=0.12

PKG_CHECK_MODULES([EVENTD], [eventd >= ${eventd_min_version}])

AC_ARG_WITH([eventdeventdir], AS_HELP_STRING([--with-eventdeventdir=DIR], [Directory for eventd event files]), [], [with_eventdeventdir=yes])
case "${with_eventdeventdir}" in
    no|"") AC_MSG_ERROR([*** You must define eventdeventdir]) ;;
    yes) eventdeventdir="`${PKG_CONFIG} ${pkg_config_extra_args} --variable=eventdir eventd`" ;;
    *) eventdeventdir="${with_eventdeventdir}" ;;
esac
AC_SUBST([eventdeventdir])

AC_CONFIG_FILES([
    Makefile
    po/Makefile.in
])
AC_OUTPUT

AC_MSG_RESULT([
    ${PACKAGE_NAME} ${PACKAGE_VERSION}

])
