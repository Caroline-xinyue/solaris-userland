#
# CDDL HEADER START
#
# The contents of this file are subject to the terms of the
# Common Development and Distribution License (the "License").
# You may not use this file except in compliance with the License.
#
# You can obtain a copy of the license at usr/src/OPENSOLARIS.LICENSE
# or http://www.opensolaris.org/os/licensing.
# See the License for the specific language governing permissions
# and limitations under the License.
#
# When distributing Covered Code, include this CDDL HEADER in each
# file and include the License file at usr/src/OPENSOLARIS.LICENSE.
# If applicable, add the following below this CDDL HEADER, with the
# fields enclosed by brackets "[]" replaced with your own identifying
# information: Portions Copyright [yyyy] [name of copyright owner]
#
# CDDL HEADER END
#

#
# Copyright (c) 2012, 2017, Oracle and/or its affiliates. All rights reserved.
#

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=		jsonrpclib
COMPONENT_VERSION=	0.2.6
COMPONENT_PROJECT_URL=	https://github.com/tcalmant/jsonrpclib
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	v$(COMPONENT_VERSION).tar.gz
COMPONENT_ARCHIVE_HASH=	\
    sha256:17acc9f89f74fd9f4a22b2fe4bd26a97a7fe68a5ea0a9bd506fb96685cb0fed2
COMPONENT_ARCHIVE_URL=https://github.com/tcalmant/jsonrpclib/archive/$(COMPONENT_ARCHIVE)
COMPONENT_BUGDB=	python-mod/jsonrpclib
COMPONENT_ANITYA_ID=	13247

TPNO=			24886

# upstream not Python 3.5 ready
PYTHON_VERSIONS=	$(PYTHON2_VERSIONS) 3.4

include $(WS_MAKE_RULES)/prep.mk
include $(WS_MAKE_RULES)/setup.py.mk
include $(WS_MAKE_RULES)/ips.mk

ASLR_MODE = $(ASLR_NOT_APPLICABLE)

COMPONENT_TEST_DIR=	$(COMPONENT_SRC)
COMPONENT_TEST_CMD= /usr/bin/nosetests
COMPONENT_TEST_ARGS = tests
COMPONENT_TEST_MASTER = $(COMPONENT_TEST_RESULTS_DIR)/results-all.master

COMPONENT_TEST_TRANSFORMS += \
    '-e "s|\(127.0.0.1\).*|\1|" ' \
    '-e "s|\(^Ran 51 tests in\).*|\1|" '

# common targets
build:		$(BUILD_NO_ARCH)

install:	$(INSTALL_NO_ARCH)

# Ran 51 tests, OK.
test:		$(TEST_NO_ARCH)

system-test:    $(SYSTEM_TESTS_NOT_IMPLEMENTED)

