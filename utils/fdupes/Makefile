#
# Copyright (C) 2008-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=fdupes
PKG_VERSION:=1.40
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://premium.caribe.net/~adrian2/programs/$(PKG_SOURCE)
PKG_MD5SUM:=11de9ab4466089b6acbb62816b30b189

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/fdupes
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Fdupes
  URL:=http://premium.caribe.net/~adrian2/fdupes.html
endef

define Package/fdupes/description
	FDUPES is a program for identifying or deleting duplicate files residing within specified directories.
endef

MAKE_FLAGS += \
	CFLAGS="$(TARGET_CFLAGS) -DVERSION=$(PKG_VERSION)" \
	LDFLAGS="$(TARGET_LDLAGS)"

define Package/fdupes/install
	$(INSTALL_DIR) $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/$(PKG_NAME) $(1)/usr/bin/
endef

$(eval $(call BuildPackage,fdupes))
