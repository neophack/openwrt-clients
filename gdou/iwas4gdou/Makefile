# 
# Copyright (C) 2006-2008 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/kernel.mk

PKG_NAME:=iwas4gdou
PKG_VERSION:=1.0
PKG_RELEASE:=1
PKG_SOURCE_URL:=http://git.oschina.net/neophack/files/raw/master/
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_MD5SUM:=d58752879da64c44d8b01cf04ed51f63

include $(INCLUDE_DIR)/package.mk

define Package/iwas4gdou
  SECTION:=net
  CATEGORY:=Network
  TITLE:=I was for GDOU 802.1X client program
  URL:=http://github.com/neophack/iwas4gdou
  DEPENDS:=+libpcap
endef

define Package/iwas4gdou/description
 802.1X client from Guangdong Ocean University
endef

define Build/Prepare
$(call Build/Prepare/Default)
endef

define Build/Configure
$(call Build/Configure/Default)
endef

define Package/iwas4gdou/install
	$(MAKE) -C $(PKG_BUILD_DIR) install-exec DESTDIR=$(1)
endef

$(eval $(call BuildPackage,iwas4gdou))
