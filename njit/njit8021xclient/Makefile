# 
# Copyright (C) 2006 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

source_id:=neophack
PKG_NAME:=njit8021xclient
PKG_RELEASE:=testing
PKG_VERSION:=v1.3.1

PKG_SOURCE_URL:=https://github.com/$(source_id)/$(PKG_NAME)/archive/
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_MD5SUM:=f7c4df3f4126b57b8f8ee92bdce011c7

PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/njit8021xclient
  SECTION:=net
  CATEGORY:=Network
  TITLE:=NJIT 802.1X client program
  URL:=https://github.com/$(source_id)/$(PKG_NAME)
  DEPENDS:=+libpcap
  PKG_BUILD_DEPENDS:=+libopenssl
endef

define Build/Configure
$(call Build/Configure/Default)
endef

define Package/njit8021xclient/install
$(MAKE) -C $(PKG_BUILD_DIR) install DESTDIR=$(1)
endef

define Package/njit8021xclient/conffiles
/etc/config/njit8021xclient.conf
endef

define Package/luci-app-njitclient
  SECTION:=net
  CATEGORY:=Network
  TITLE:=LuCI pages for NJIT 802.1X client
  URL:=https://github.com/$(source_id)/luci-app-njitclient
  DEPENDS:=njit8021xclient
  PKGARCH:=all
endef

define Package/njit8021xclient/description
  $(call Package/njit8021xclient/Default/description)
  This package contains only the main program njit-client.
endef

$(eval $(call BuildPackage,njit8021xclient))
