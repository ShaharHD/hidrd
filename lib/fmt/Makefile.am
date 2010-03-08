#
# Copyright (C) 2010 Nikolai Kondrashov
#
# This file is part of hidrd.
#
# Hidrd is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; either version 2 of the License, or
# (at your option) any later version.
#
# Hidrd is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with hidrd; if not, write to the Free Software
# Foundation, Inc., 51 Franklin St, Fifth Floor, Boston, MA  02110-1301  USA

SUBDIRS = natv

lib_LTLIBRARIES = libhidrd_fmt.la

libhidrd_fmt_la_SOURCES = \
    inst.c                  \
    list.c                  \
    natv.c

libhidrd_fmt_la_LIBADD = \
    ../item/libhidrd_item.la    \
    ../opt/libhidrd_opt.la      \
    natv/libhidrd_natv.la

TESTS = hidrd_natv_test

hidrd_natv_test_SOURCES = natv_test.c
hidrd_natv_test_LDADD = ../strm/libhidrd_strm.la $(lib_LTLIBRARIES)

if ENABLE_FMT_XML
SUBDIRS += xml
libhidrd_fmt_la_SOURCES += xml.c
libhidrd_fmt_la_CFLAGS = @LIBXML2_CFLAGS@
libhidrd_fmt_la_LDFLAGS = @LIBXML2_LIBS@
libhidrd_fmt_la_LIBADD += xml/libhidrd_xml.la

TESTS += hidrd_xml_test
hidrd_xml_test_CFLAGS = @LIBXML2_CFLAGS@
hidrd_xml_test_SOURCES = xml_test.c
hidrd_xml_test_LDADD = ../strm/libhidrd_strm.la $(lib_LTLIBRARIES)
endif

bin_PROGRAMS =
check_PROGRAMS = $(TESTS)

if ENABLE_TESTS_INSTALL
bin_PROGRAMS += $(TESTS)
endif