m4_define([v_maj], [2])
m4_define([v_min], [6])
m4_define([v_pat], [1])
m4_define([project_version], [v_maj.v_min.v_pat])

AC_INIT([http_parser], [project_version], [https://github.com/nodejs/http-parser/issues], [], [https://github.com/nodejs/http-parser])
AC_PREREQ(2.63)
AC_CONFIG_SRCDIR([src/http_parser.h])
AC_CONFIG_AUX_DIR([build])
AC_CONFIG_MACRO_DIR([build])
AC_CONFIG_HEADER([config.h])

AX_DEFINE_ABI_VERSION([1], [0], [0])
AC_DEFINE([HTTP_PARSER_VERSION_MAJOR], [v_maj],     [Set the major version.])
AC_DEFINE([HTTP_PARSER_VERSION_MINOR], [v_min],     [Set the minor version.])
AC_DEFINE([HTTP_PARSER_VERSION_PATCH], [v_pat],     [Set the patch version.])

AM_INIT_AUTOMAKE([-Wall -Werror foreign subdir-objects])

AC_PROG_CC
AC_PROG_INSTALL

m4_ifdef([AM_PROG_AR], [AM_PROG_AR])
LT_INIT

PKG_PROG_PKG_CONFIG
AC_C_INLINE

AC_ARG_WITH([pkgconfigdir],
    AS_HELP_STRING([--with-pkgconfigdir=PATH],
        [Path to the pkgconfig directory [[LIBDIR/pkgconfig]]]),
    [pkgconfigdir="$withval"],
    [pkgconfigdir='${libdir}/pkgconfig'])
AC_SUBST([pkgconfigdir])


AC_CONFIG_FILES([Makefile contrib/redhat/rpm.spec pkg/http_parser.pc])
AC_OUTPUT
