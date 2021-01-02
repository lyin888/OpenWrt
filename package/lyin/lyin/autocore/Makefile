# Copyright (C) 2010-2011 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=autocore
PKG_VERSION:=1
PKG_RELEASE:=36

include $(INCLUDE_DIR)/package.mk

define Package/autocore-x86
  TITLE:=x86/x64 auto core loadbalance script.
  MAINTAINER:=Lean
  DEPENDS:=@TARGET_x86 +bc +lm-sensors +ethtool
  VARIANT:=x86
endef

define Package/autocore-arm/description
  A luci autoconfig hotplug script.
endef

define Package/autocore-x86/description
  A usb autoconfig hotplug script.
endef

define Build/Compile
endef

define Package/autocore-x86/install
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/x86/autocore $(1)/etc/init.d/autocore
	$(INSTALL_DIR) $(1)/etc
	$(INSTALL_DATA) ./files/x86/index.htm $(1)/etc/index.htm
	$(INSTALL_DIR) $(1)/sbin
	$(CP) ./files/x86/sbin/* $(1)/sbin
endef

$(eval $(call BuildPackage,autocore-x86))
