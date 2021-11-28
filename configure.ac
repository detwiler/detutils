#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_INIT([detutils],
        [m4_esyscmd([build-aux/git-version-gen .tarball-version])],
        [mike@detwiler.io])

AC_PREREQ([2.64])
AC_CONFIG_AUX_DIR([build-aux])
AC_CONFIG_MACRO_DIR([m4])
AC_CONFIG_SRCDIR([src/get-git.in])

AM_INIT_AUTOMAKE([-Wall -Werror -Wno-portability foreign])
AM_SILENT_RULES([yes])

AC_CANONICAL_HOST

# Checks for programs.
AC_PROG_GREP
AC_PROG_INSTALL
AC_PROG_LN_S
AC_PROG_SED

AC_ARG_VAR([BASENC], [path to basenc])
AC_CHECK_PROGS([BASENC], [basenc gbasenc], [no])
AM_CONDITIONAL([HAVE_BASENC],
               [test "x$BASENC" != xno])

QH_REQUIRE_PROG([BASE64], [base64 gbase64], [path to base64])
QH_REQUIRE_PROG([CONAN], [conan], [path to conan])
QH_REQUIRE_PROG([CSCOPE_PATH], [cscope], [path to cscope])
QH_REQUIRE_PROG([CURL], [curl], [path to curl])

AC_CACHE_CHECK([for cut that supports --delimiter], [ac_cv_path_CUT],
  [AC_PATH_PROGS_FEATURE_CHECK([CUT], [cut gcut],
    [$ac_path_CUT --delimiter=' ' --fields=1 </dev/null &>/dev/null \
      && ac_cv_path_CUT=$ac_path_CUT ac_path_CUT_found=:],
    [AC_MSG_ERROR([could not find cut that supports --delimiter])])])
AC_SUBST([CUT], [$ac_cv_path_CUT])

QH_REQUIRE_PROG([DOS2UNIX], [dos2unix], [path to dos2unix])
QH_REQUIRE_PROG([ENV], [env], [path to env])
QH_REQUIRE_PROG([FILE], [file], [path to file])
QH_REQUIRE_PROG([GPG], [gpg2 gpg], [path to gpg])

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

QH_REQUIRE_PROG([SHA1SUM], [sha1sum gsha1sum], [path to sha1sum])
QH_REQUIRE_PROG([SHA224SUM], [sha224sum gsha224sum], [path to sha224sum])
QH_REQUIRE_PROG([SHA256SUM], [sha256sum gsha256sum], [path to sha256sum])
QH_REQUIRE_PROG([SHA384SUM], [sha384sum gsha384sum], [path to sha384sum])
QH_REQUIRE_PROG([SHA512SUM], [sha512sum gsha512sum], [path to sha512sum])

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

QH_REQUIRE_PROG([UUENCODE], [uuencode], [path to uuencode])

AC_CACHE_CHECK([for wc that supports --lines], [ac_cv_path_WC],
  [AC_PATH_PROGS_FEATURE_CHECK([WC], [wc gwc],
    [$ac_path_WC --lines </dev/null &>/dev/null \
      && ac_cv_path_WC=$ac_path_WC ac_path_WC_found=:],
    [AC_MSG_ERROR([could not find wc that supports --lines])])])
AC_SUBST([WC], [$ac_cv_path_WC])

QH_REQUIRE_PROG([WGET], [wget], [path to wget])
QH_REQUIRE_PROG([XXD], [xxd], [path to xxd])
QH_REQUIRE_PROG([ZCAT], [zcat], [path to zcat])

# Checks for files.

# Additional options
QH_VAR_ENSURE([GIT_BASE_URL],
              [Base URL for git downloads],
              ['http://www.kernel.org/pub/software/scm'])

QH_VAR_ENSURE([GNU_BASE_URL],
              [Base URL for GNU downloads],
              ['http://ftp.gnu.org/gnu'])

# Option to enable minicom
QH_ARG_ENABLE([minicom], [yes])
AM_CONDITIONAL([ENABLE_MINICOM],
               [test "x$enable_minicom" = xyes])

# Check for minicom if minicom is enabled
AM_COND_IF([ENABLE_MINICOM],
           [QH_REQUIRE_PROG([MINICOM], [minicom], [path to minicom])])

AC_CONFIG_FILES([Makefile
                 src/Makefile
                 src/config-bash
                 src/makecscope
                 src/script-functions
                 ])

AC_OUTPUT
