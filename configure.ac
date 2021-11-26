#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_INIT([detutils],
        [m4_esyscmd([build-aux/git-version-gen .tarball-version])],
        [mike@detwiler.io])

AC_PREREQ([2.63])
AC_CONFIG_AUX_DIR([build-aux])
AC_CONFIG_MACRO_DIR([m4])
AC_CONFIG_SRCDIR([src/get-git.in])

AM_INIT_AUTOMAKE([-Wall -Wno-portability -Werror dist-bzip2])
AM_SILENT_RULES([yes])

AC_CANONICAL_HOST

# Checks for programs.
AC_PROG_GREP
AC_PROG_INSTALL
AC_PROG_LN_S
AC_PROG_SED

AC_ARG_VAR([ASCII85], [path to ascii85])
AC_CHECK_PROGS([ASCII85], [ascii85], [no])
AS_IF([test "x$ASCII85" = xno],
      [AC_MSG_ERROR([could not find ascii85; install rubygem-Ascii85])])

AC_ARG_VAR([BASE64], [GNU coreutils base64])
AC_CHECK_PROGS([BASE64], [base64 gbase64], [no])
AS_IF([test "x$BASE64" = xno],
      [AC_MSG_ERROR([could not find GNU coreutils base64])])

AC_ARG_VAR([CONAN], [path to conan])
AC_CHECK_PROGS([CONAN], [conan], [no])
AS_IF([test "x$CONAN" = xno],
      [AC_MSG_ERROR([could not find conan; pip install conan])])

AC_ARG_VAR([CSCOPEPRG], [path to cscope])
AC_CHECK_PROGS([CSCOPEPRG], [cscope], [no])
AS_IF([test "x$CSCOPEPRG" = xno],
      [AC_MSG_ERROR([could not find cscope])])

AC_ARG_VAR([CURL], [path to curl])
AC_PATH_PROG([CURL], [curl], [no])
AS_IF([test "x$CURL" = xno],
      [AC_MSG_ERROR([cannot find curl])])

AC_CACHE_CHECK([for cut that supports --delimiter], [ac_cv_path_CUT],
  [AC_PATH_PROGS_FEATURE_CHECK([CUT], [cut gcut],
    [$ac_path_CUT --delimiter=' ' --fields=1 </dev/null &>/dev/null \
      && ac_cv_path_CUT=$ac_path_CUT ac_path_CUT_found=:],
    [AC_MSG_ERROR([could not find cut that supports --delimiter])])])
AC_SUBST([CUT], [$ac_cv_path_CUT])

AC_ARG_VAR([DOS2UNIX], [path to dos2unix])
AC_CHECK_PROGS([DOS2UNIX], [dos2unix], [no])
AS_IF([test "x$DOS2UNIX" = xno],
      [AC_MSG_ERROR([could not find dos2unix])])

AC_ARG_VAR([ENV], [path to env])
AC_PATH_PROG([ENV], [env], [no])
AS_IF([test "x$ENV" = xno],
      [AC_MSG_ERROR([cannot find env])])

AC_ARG_VAR([FILE], [path to file])
AC_PATH_PROG([FILE], [file], [no])
AS_IF([test "x$FILE" = xno],
      [AC_MSG_ERROR([cannot find file program])])

AC_ARG_VAR([GPG], [GNU gpg])
AC_CHECK_PROGS([GPG], [gpg2 gpg], [no])
AS_IF([test "x$GPG" = xno],
      [AC_MSG_ERROR([could not find GNU gpg])])

AC_CACHE_CHECK([for head that supports --bytes], [ac_cv_path_HEAD],
  [AC_PATH_PROGS_FEATURE_CHECK([HEAD], [head ghead],
    [$ac_path_HEAD --bytes=1 </dev/null &>/dev/null \
      && ac_cv_path_HEAD=$ac_path_HEAD ac_path_HEAD_found=:],
    [AC_MSG_ERROR([could not find head that supports --bytes])])])
AC_SUBST([HEAD], [$ac_cv_path_HEAD])

AC_CACHE_CHECK([for mktemp that supports --directory], [ac_cv_path_MKTEMP],
  [AC_PATH_PROGS_FEATURE_CHECK([MKTEMP], [mktemp gmktemp],
    [$ac_path_MKTEMP --dry-run --directory &>/dev/null \
      && ac_cv_path_MKTEMP=$ac_path_MKTEMP ac_path_MKTEMP=:],
    [AC_MSG_ERROR([could not find mktemp that supports --directory])])])
AC_SUBST([MKTEMP], [$ac_cv_path_MKTEMP])

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

AC_CACHE_CHECK([for stat that supports --printf], [ac_cv_path_STAT],
  [AC_PATH_PROGS_FEATURE_CHECK([STAT], [stat gstat],
    [$ac_path_STAT --printf='%s' /dev/null &>/dev/null \
      && ac_cv_path_STAT=$ac_path_STAT ac_path_STAT=:],
    [AC_MSG_ERROR([could not find stat that supports --printf])])])
AC_SUBST([STAT], [$ac_cv_path_STAT])

AC_CACHE_CHECK([for tail that supports --bytes], [ac_cv_path_TAIL],
  [AC_PATH_PROGS_FEATURE_CHECK([TAIL], [tail gtail],
    [$ac_path_TAIL --bytes=1 </dev/null &>/dev/null \
      && ac_cv_path_TAIL=$ac_path_TAIL ac_path_TAIL_found=:],
    [AC_MSG_ERROR([could not find tail that supports --bytes])])])
AC_SUBST([TAIL], [$ac_cv_path_TAIL])

AC_CACHE_CHECK([for tr that supports --delete], [ac_cv_path_TR],
  [AC_PATH_PROGS_FEATURE_CHECK([TR], [tr gtr],
    [$ac_path_TR --delete ' ' </dev/null &>/dev/null \
      && ac_cv_path_TR=$ac_path_TR ac_path_TR_found=:],
    [AC_MSG_ERROR([could not find tr that supports --delete])])])
AC_SUBST([TR], [$ac_cv_path_TR])

AC_ARG_VAR([UUENCODE], [path to uuencode])
AC_CHECK_PROGS([UUENCODE], [uuencode], [no])
AS_IF([test "x$UUENCODE" = xno],
      [AC_MSG_ERROR([could not find uuencode; install GNU sharutils])])

AC_CACHE_CHECK([for wc that supports --lines], [ac_cv_path_WC],
  [AC_PATH_PROGS_FEATURE_CHECK([WC], [wc gwc],
    [$ac_path_WC --lines </dev/null &>/dev/null \
      && ac_cv_path_WC=$ac_path_WC ac_path_WC_found=:],
    [AC_MSG_ERROR([could not find wc that supports --lines])])])
AC_SUBST([WC], [$ac_cv_path_WC])

AC_ARG_VAR([WGET], [wget])
AC_CHECK_PROGS([WGET], [wget], [no])
AS_IF([test "x$WGET" = xno],
      [AC_MSG_ERROR([could not find wget])])

AC_ARG_VAR([XXD], [xxd])
AC_CHECK_PROGS([XXD], [xxd], [no])
AS_IF([test "x$XXD" = xno],
      [AC_MSG_ERROR([could not find xxd; install vim-common])])

AC_ARG_VAR([ZCAT], [zcat])
AC_CHECK_PROGS([ZCAT], [zcat], [no])
AS_IF([test "x$ZCAT" = xno],
      [AC_MSG_ERROR([could not find zcat])])

# Checks for files.

# Additional options

# option to specify git source base url
DET_ARG_WITH([git_base_url], [http://www.kernel.org/pub/software/scm])
AC_SUBST([GIT_BASE_URL], [$with_git_base_url])

# option to specify GNU tool source base url
DET_ARG_WITH([gnu_base_url], [http://ftp.gnu.org/gnu])
AC_SUBST([GNU_BASE_URL], [$with_gnu_base_url])

# Option to enable minicom
DET_ARG_ENABLE([minicom], [no])
AM_CONDITIONAL([ENABLE_MINICOM],
               [test "x$enable_minicom" = xyes])

# Check for minicom if minicom is enabled
AM_COND_IF([ENABLE_MINICOM],
           [AC_ARG_VAR([MINICOM], [minicom])
            AC_CHECK_PROGS([MINICOM], [minicom], [no])
            AS_IF([test "x$MINICOM" = xno],
                  [AC_MSG_ERROR([could not find minicom])])])

AC_CONFIG_FILES([Makefile
                 scripts/Makefile
                 scripts/config-bash
                 scripts/makecscope
                 scripts/script-functions
                 ])

AC_OUTPUT
