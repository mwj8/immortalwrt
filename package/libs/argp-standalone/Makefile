#
# Copyright (C) 2007-2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=argp-standalone
PKG_VERSION:=1.3
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://www.lysator.liu.se/~nisse/misc/
PKG_HASH:=dec79694da1319acd2238ce95df57f3680fea2482096e483323fddf3d818d8be
PKG_MAINTAINER:=Ted Hess <thess@kitschensync.net>

PKG_LICENSE:=LGPL-2.1
PKG_LICENSE:=Makefile.am

include $(INCLUDE_DIR)/package.mk

define Package/argp-standalone
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=Hierarchial argument parsing broken out from glibc
  URL:=http://www.lysator.liu.se/~nisse/misc/
endef

define Package/argp-standalone/description
  GNU libc hierarchial argument parsing library broken out from glibc.
endef

MAKE_FLAGS += \
	CFLAGS="$(TARGET_CFLAGS) $(FPIC) -std=gnu89"

HOST_MAKE_FLAGS += \
	CFLAGS="$(HOST_CFLAGS) $(FPIC) -std=gnu89"

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(CP)   $(PKG_BUILD_DIR)/argp.h \
		$(1)/usr/include/
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP)   $(PKG_BUILD_DIR)/libargp.a \
		$(1)/usr/lib/
endef

$(eval $(call BuildPackage,argp-standalone))
