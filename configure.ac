AC_INIT(dpaste, 0.0.1)
AC_CONFIG_AUX_DIR(ac)
AM_INIT_AUTOMAKE([foreign subdir-objects])
AC_CONFIG_HEADERS([config.h])
AC_CONFIG_MACRO_DIR([m4])
AC_CANONICAL_HOST

AC_ARG_ENABLE([debug], AS_HELP_STRING([--enable-debug], [Build in debug mode, adds stricter warnings, disables optimization]))
AS_IF([test "x$enable_debug" = "xyes"],
      [CXXFLAGS="${CXXFLAGS} -g -Wno-return-type -Wall -Wextra -Wnon-virtual-dtor -O0"],
      [CXXFLAGS="${CXXFLAGS} -O3"])

AC_PROG_CXX

AX_CXX_COMPILE_STDCXX(11,[noext],[mandatory])

PKG_CHECK_MODULES([OpenDHT], [opendht >= 1.2])

AC_CONFIG_FILES([Makefile
                 src/Makefile])
AC_OUTPUT
