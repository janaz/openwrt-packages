#
# Copyright (C) 2011 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=shairport-janaz
PKG_VERSION:=0.01
PKG_RELEASE:=$(PKG_SOURCE_VERSION)

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=git://github.com/abrasive/shairport.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=d679d19a4bd66cc220dabfd23ad748c34e95995c
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz

PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/shairport-janaz/Default
  SECTION:=sound
  CATEGORY:=Sound
  TITLE:=ShairPort-janaz
  URL:=https://github.com/janaz/
endef


define Package/shairport-janaz
  $(Package/shairport-janaz/Default)
  DEPENDS:= +libopenssl +libao +avahi-daemon +libavahi-dbus-support +avahi-utils
endef


define Package/shairport-janaz/description
  ShairPort is server software that implements the RAOP protocol for
  playback of music streamed from a compatible remote client.
endef


define Package/shairport-janaz/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/shairport $(1)/usr/bin/
	$(INSTALL_DIR) $(1)/etc/init.d/
	$(INSTALL_BIN) files/shairport.init $(1)/etc/init.d/shairport-janaz
endef



$(eval $(call BuildPackage,shairport-janaz))
