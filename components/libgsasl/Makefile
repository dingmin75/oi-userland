#
# This file and its contents are supplied under the terms of the
# Common Development and Distribution License ("CDDL)". You may
# only use this file in accordance with the terms of the CDDL.
#
# A full copy of the text of the CDDL should have accompanied this
# source. A copy of the CDDL is also available via the Internet at
# http://www.illumos.org/license/CDDL.
#

#
# Copyright (c) 2014 Alexander Pyhalov. All rights reserved
#

include ../../make-rules/shared-macros.mk

COMPONENT_NAME=		libgsasl
COMPONENT_VERSION=	1.8.0
COMPONENT_PROJECT_URL=	http://www.gnu.org/software/gsasl/
COMPONENT_SUMMARY=	Implementation of the Simple Authentication and Security Layer framework 
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH=	\
	sha256:3adfb49f9c92a719dea855fd1840d698cde55d4648d332a69032ba8bea207720
COMPONENT_FMRI=		library/libgsasl
COMPONENT_CLASSIFICATION=	System/Libraries
COMPONENT_LICENSE= GPLv3
COMPONENT_LICENSE_FILE= COPYING
    
COMPONENT_ARCHIVE_URL=	ftp://ftp.gnu.org/gnu/gsasl/$(COMPONENT_ARCHIVE)

include $(WS_TOP)/make-rules/prep.mk
include $(WS_TOP)/make-rules/configure.mk
include $(WS_TOP)/make-rules/ips.mk

PATH=/usr/gnu/bin:/usr/bin

CFLAGS+= -I/usr/include/idn

CONFIGURE_OPTIONS.32 += --sysconfdir=/etc
CONFIGURE_OPTIONS.32 += --libexecdir=/usr/lib
CONFIGURE_OPTIONS.64 += --libexecdir=/usr/lib/$(MACH64)

# common targets
build:		$(BUILD_32_and_64)

install:	$(INSTALL_32_and_64)

test:		$(TEST_32_and_64)

BUILD_PKG_DEPENDENCIES = $(BUILD_TOOLS)

include $(WS_TOP)/make-rules/depend.mk
