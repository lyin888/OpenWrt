#
# Copyright (C) 2010-2011 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=mw4530r
PKG_VERSION:=1
PKG_RELEASE:=1


include $(INCLUDE_DIR)/package.mk

define Package/mw4530r
  TITLE:=Mercury MW4530R personalized.
  MAINTAINER:=lyin
  DEPENDS:=@TARGET_ar71xx
endef

define Package/mw4530r/description
Mercury MW4530R personalized.
endef

define Build/Compile
endef

define Package/mw4530r/install
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/mw4530r $(1)/etc/init.d/mw4530r
	$(INSTALL_DIR) $(1)/etc
	$(INSTALL_DATA) ./files/index.htm $(1)/etc/index.htm
	$(INSTALL_DIR) $(1)/etc
	$(INSTALL_BIN) ./files/boot $(1)/etc/boot
	$(INSTALL_DIR) $(1)/bin
	$(CP) ./files/inform $(1)/bin
endef

$(eval $(call BuildPackage,mw4530r))
