AC_PREREQ([2.61])
AC_INIT([libnsh], [0.4], [https://github.com/westermo/libnsh/issues])
AC_CONFIG_AUX_DIR(auxdata)
AM_INIT_AUTOMAKE([1.11 foreign -W -Wall -Wextra])
AM_SILENT_RULES([yes])
AC_CONFIG_MACRO_DIR([m4])

AC_CONFIG_SRCDIR([src/nsh.h])
AC_CONFIG_HEADERS([config.h])
AC_CONFIG_FILES([Makefile src/Makefile examples/Makefile test/Makefile libnsh.pc])

AC_PROG_CC
AM_PROG_AR
LT_INIT

PKG_CHECK_MODULES([CHECK], [check >= 0.9.4], [have_check=yes], [have_check=no])

# Optional building of examples
AC_ARG_ENABLE([examples],
	[AC_HELP_STRING([--enable-examples], [build examples in examples])],
	[enable_examples=yes], [])

AM_CONDITIONAL([ENABLE_EXAMPLES], [test "$enable_examples" = yes])
AM_CONDITIONAL([HAVE_CHECK],      [test "$have_check"      = yes])

AC_OUTPUT
