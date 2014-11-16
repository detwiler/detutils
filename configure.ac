#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_INIT([detutils],
        [m4_esyscmd([build-aux/git-version-gen .tarball-version])],
        [mike@detwiler.io])

AC_PREREQ([2.63])
AC_CONFIG_AUX_DIR([build-aux])
AC_CONFIG_MACRO_DIR([m4])
AC_CONFIG_SRCDIR([scripts/get-git.in])

AM_INIT_AUTOMAKE([-Wall -Wno-portability -Werror dist-bzip2])
AM_SILENT_RULES([yes])

AC_CANONICAL_HOST

# Checks for programs.
AC_PROG_INSTALL
AC_PROG_LN_S
AC_PROG_SED
AM_CONDITIONAL([HAVE_SED], [test "x$SED" != x])

AC_ARG_VAR([SHA1SUM], [GNU coreutils sha1sum])
AC_CHECK_PROGS([SHA1SUM], [sha1sum gsha1sum], [no])
AS_IF([test "x$SHA1SUM" = xno],
      [AC_MSG_ERROR([could not find GNU coreutils sha1sum])])

AC_ARG_VAR([SHA224SUM], [GNU coreutils sha224sum])
AC_CHECK_PROGS([SHA224SUM], [sha224sum gsha224sum], [no])
AS_IF([test "x$SHA224SUM" = xno],
      [AC_MSG_ERROR([could not find GNU coreutils sha224sum])])

AC_ARG_VAR([SHA256SUM], [GNU coreutils sha256sum])
AC_CHECK_PROGS([SHA256SUM], [sha256sum gsha256sum], [no])
AS_IF([test "x$SHA256SUM" = xno],
      [AC_MSG_ERROR([could not find GNU coreutils sha256sum])])

AC_ARG_VAR([SHA384SUM], [GNU coreutils sha384sum])
AC_CHECK_PROGS([SHA384SUM], [sha384sum gsha384sum], [no])
AS_IF([test "x$SHA384SUM" = xno],
      [AC_MSG_ERROR([could not find GNU coreutils sha384sum])])

AC_ARG_VAR([SHA512SUM], [GNU coreutils sha512sum])
AC_CHECK_PROGS([SHA512SUM], [sha512sum gsha512sum], [no])
AS_IF([test "x$SHA512SUM" = xno],
      [AC_MSG_ERROR([could not find GNU coreutils sha512sum])])

AC_ARG_VAR([BASE64], [GNU coreutils base64])
AC_CHECK_PROGS([BASE64], [base64 gbase64], [no])
AS_IF([test "x$BASE64" = xno],
      [AC_MSG_ERROR([could not find GNU coreutils base64])])

AC_ARG_VAR([UUENCODE], [path to uuencode])
AC_CHECK_PROGS([UUENCODE], [uuencode], [no])
AS_IF([test "x$UUENCODE" = xno],
      [AC_MSG_ERROR([could not find uuencode; install GNU sharutils])])

AC_ARG_VAR([XXD], [xxd])
AC_CHECK_PROGS([XXD], [xxd], [no])
AS_IF([test "x$XXD" = xno],
      [AC_MSG_ERROR([could not find xxd; install vim-common])])

AC_ARG_VAR([ASCII85], [path to ascii85])
AC_CHECK_PROGS([ASCII85], [ascii85], [no])
AS_IF([test "x$ASCII85" = xno],
      [AC_MSG_ERROR([could not find ascii85; install rubygem-Ascii85])])

AC_ARG_VAR([GPG], [GNU gpg])
AC_CHECK_PROGS([GPG], [gpg2 gpg], [no])
AS_IF([test "x$GPG" = xno],
      [AC_MSG_ERROR([could not find GNU gpg])])

# Checks for files.

# Additional options

AC_CONFIG_FILES([Makefile
                 scripts/Makefile
                 scripts/config-bash
                 scripts/dl-gnu-tool
                 scripts/script-functions
                 scripts/gen-pass
                 scripts/upper2lower
                 ])

AC_OUTPUT
