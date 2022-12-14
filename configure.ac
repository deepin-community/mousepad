dnl
dnl This file was autogenerated from "configure.ac.in".
dnl Edit that file instead!
dnl

dnl ***************************
dnl *** Version information ***
dnl ***************************
m4_define([mousepad_version_major], [0])
m4_define([mousepad_version_minor], [5])
m4_define([mousepad_version_micro], [2])
m4_define([mousepad_version_nano], []) dnl leave this empty to have no nano version
m4_define([mousepad_version_build], [fb273b6])
m4_define([mousepad_version_tag], [])
m4_define([mousepad_version], [mousepad_version_major().mousepad_version_minor().mousepad_version_micro()ifelse(mousepad_version_nano(), [], [], [.mousepad_version_nano()])ifelse(mousepad_version_tag(), [git], [mousepad_version_tag()-mousepad_version_build()], [mousepad_version_tag()])])

dnl *******************************************
dnl *** Debugging support for GIT snapshots ***
dnl *******************************************
m4_define([mousepad_debug_default], [ifelse(mousepad_version_tag(), [git], [yes], [minimum])])

dnl ***************************
dnl *** Initialize autoconf ***
dnl ***************************
AC_COPYRIGHT([Copyright (C) 2005-2021
        The Mousepad developers. All rights reserved.])
AC_INIT([Mousepad], [mousepad_version], [https://gitlab.xfce.org/apps/mousepad], [mousepad])
AC_PREREQ([2.50])
AC_CONFIG_MACRO_DIRS([m4])
AC_CANONICAL_TARGET()
AC_REVISION([])

dnl ***************************
dnl *** Initialize automake ***
dnl ***************************
AM_INIT_AUTOMAKE([1.8 no-dist-gzip dist-bzip2 tar-ustar foreign])
AC_CONFIG_HEADERS([config.h])
AM_MAINTAINER_MODE()
m4_ifdef([AM_SILENT_RULES], [AM_SILENT_RULES([yes])])

dnl *******************************
dnl *** Check for UNIX variants ***
dnl *******************************
AC_AIX()
AC_ISC_POSIX()
AC_MINIX()

dnl ********************************
dnl *** Check for basic programs ***
dnl ********************************
AC_PROG_CC()
AM_PROG_CC_C_O()
AC_PROG_LD()
AC_PROG_INSTALL()
IT_PROG_INTLTOOL([0.35.0])

dnl **************************
dnl *** Initialize libtool ***
dnl **************************
LT_PREREQ([2.2.6])
LT_INIT([disable-static])

dnl **************************************
dnl *** Substitute version information ***
dnl **************************************
MOUSEPAD_VERSION_MAJOR=mousepad_version_major()
MOUSEPAD_VERSION_MINOR=mousepad_version_minor()
MOUSEPAD_VERSION_MICRO=mousepad_version_micro()
MOUSEPAD_VERSION_NANO=mousepad_version_nano()
AC_SUBST([MOUSEPAD_VERSION_MAJOR])
AC_SUBST([MOUSEPAD_VERSION_MINOR])
AC_SUBST([MOUSEPAD_VERSION_MICRO])
AC_SUBST([MOUSEPAD_VERSION_NANO])

dnl ************************************
dnl *** Check for standard libraries ***
dnl ************************************
AC_SEARCH_LIBS([round], [m], [], [
  AC_MSG_ERROR([unable to find the round() function in math library])
])

dnl **********************************
dnl *** Check for standard headers ***
dnl **********************************
AC_CHECK_HEADERS([libintl.h locale.h math.h stdio.h stdlib.h string.h])

dnl ******************************
dnl *** Check for i18n support ***
dnl ******************************
XDT_I18N([ko hye tr it sq da fi et ug he ro hy_AM bg de zh_TW th el kk eu id es nn nb sk pt lt nl is ja ie ar uk en_AU ast fr hu hr ms sl sr zh_CN cs sv gl en_GB pt_BR oc be ru te pl ca ])

dnl ***********************************
dnl *** Check for required packages ***
dnl ***********************************
XDT_CHECK_PACKAGE([GLIB], [glib-2.0], [2.52.0])
XDT_CHECK_PACKAGE([GTHREAD], [gthread-2.0], [2.52.0])
XDT_CHECK_PACKAGE([XFCONF], [libxfconf-0], [4.12.0])
XDT_CHECK_PACKAGE([GTK], [gtk+-3.0], [3.22.0])
XDT_CHECK_PACKAGE([GTKSOURCEVIEW], [gtksourceview-3.0], [3.24.0])

dnl ************************************
dnl *** Enable support for GSettings ***
dnl ************************************
GLIB_GSETTINGS

AC_ARG_ENABLE([keyfile-settings],
              [AS_HELP_STRING([--enable-keyfile-settings],
                              [Use the GSettings keyfile backend rather than the default])],
              [enable_keyfile_settings="yes"],
              [enable_keyfile_settings="default"])

AM_CONDITIONAL([WITH_KEYFILE_SETTINGS],
               [test "x$enable_keyfile_settings" = "xyes"])

dnl ***********************************
dnl *** Check for debugging support ***
dnl ***********************************
XDT_FEATURE_DEBUG([mousepad_debug_default])

dnl **************************************
dnl *** Check for linker optimizations ***
dnl **************************************
XDT_FEATURE_LINKER_OPTS()

dnl *********************************
dnl *** Substitute platform flags ***
dnl *********************************
AC_MSG_CHECKING([PLATFORM_CPPFLAGS])
AC_MSG_RESULT([$PLATFORM_CPPFLAGS])
AC_SUBST([PLATFORM_CPPFLAGS])
AC_MSG_CHECKING([PLATFORM_CFLAGS])
AC_MSG_RESULT([$PLATFORM_CFLAGS])
AC_SUBST([PLATFORM_CFLAGS])
AC_MSG_CHECKING([PLATFORM_LDFLAGS])
AC_MSG_RESULT([$PLATFORM_LDFLAGS])
AC_SUBST([PLATFORM_LDFLAGS])

AC_OUTPUT([
Makefile
mousepad/Makefile
po/Makefile.in
icons/Makefile
icons/16x16/Makefile
icons/48x48/Makefile
icons/128x128/Makefile
icons/scalable/Makefile
])

dnl ***************************
dnl *** Print configuration ***
dnl ***************************
echo
echo "Build Configuration:"
echo
echo "* Debug Support:             $enable_debug"
echo "* Use keyfile backend:       $enable_keyfile_settings"
echo
