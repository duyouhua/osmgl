#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.63])
AC_INIT([libosmgl], [0.1])
AM_INIT_AUTOMAKE([-Wall -Werror foreign])
AC_PROG_INSTALL

# Checks for programs.
AC_PROG_CXX
AM_PROG_LEX
AC_PROG_YACC
AC_PROG_LIBTOOL

# Checks for libraries.
PKG_CHECK_MODULES([GL], [gl >= 7.7.0]) 
PKG_CHECK_MODULES([GLU], [glu >= 7.7.0]) 
PKG_CHECK_MODULES([XML], [libxml-2.0 >= 2.7.0]) 
AC_CHECK_LIB(glut, glutMainLoop)
AC_CHECK_LIB(fl, yywrap)

# Checks for header files.
AC_CHECK_HEADERS([stdint.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_HEADER_STDBOOL
AC_TYPE_UINT32_T

# Checks for library functions.
CFLAGS="-Werror -std=gnu99"
CXXFLAGS="-Werror -std=gnu++0x"

AC_MSG_CHECKING(whether to enable debugging)
debug_default="yes"

AC_ARG_ENABLE(debug, [  --enable-debug=[no/yes] turn on debugging
                       [default=$debug_default]],, enable_debug=$debug_default)
if test "x$enable_debug" = "xyes"; then
         CFLAGS="$CFLAGS -g -DOSMGL_DEBUG"
	 CXXFLAGS="$CXXFLAGS -g -DOSMGL_DEBUG"
AC_MSG_RESULT(yes)
else
AC_MSG_RESULT(no)
fi


AC_CONFIG_FILES([Makefile src/Makefile example/Makefile  pkgconfig/libosmgl.pc])
AC_OUTPUT
