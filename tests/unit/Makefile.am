LIBS = @ZORP_LIBS@ @MODULES_LIBS@ @DEPS_LIBS@
LDADD = -lboost_unit_test_framework -lstdc++
CPPFLAGS = @MODULES_CPPFLAGS@ -DBOOST_TEST_DYN_LINK=1

check_PROGRAMS = \
	test_dhparam \
	test_pystruct \
	test_szig

check_SCRIPTS = test_logger.py

test_dhparam_SOURCES = test_dhparam.cc
test_pystruct_SOURCES = test_pystruct.cc
test_szig_SOURCES = test_szig.cc
test_dynexpect_SOURCES = test_dynexpect.cc
test_proxy_SOURCES = helpers/zproxy.cc

AM_TESTS_ENVIRONMENT = G_DEBUG='fatal_warnings gc-friendly'; G_SLICE='always-malloc'; PYTHONPATH=${top_srcdir}/pylib:${top_builddir}/pylib/Zorp; export G_DEBUG; export G_SLICE; export PYTHONPATH;

TESTS = $(check_SCRIPTS) $(check_PROGRAMS)

EXTRA_DIST = $(check_SCRIPTS) pystruct.py helpers/zproxy.h helpers/start_audit.h
