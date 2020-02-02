#
# Copyright (C) 2010-2011 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=ipq40xx
PKG_VERSION:=1
PKG_RELEASE:=1


include $(INCLUDE_DIR)/package.mk

define Package/ipq40xx
  TITLE:=P&WR619AC auto core loadbalance script.
  MAINTAINER:=lyin
  DEPENDS:=@TARGET_ipq40xx
endef

define Package/ipq40xx/description
A usb autoconfig hotplug script.
endef

define Build/Compile
endef

define Package/ipq40xx/install
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/ipq40xx $(1)/etc/init.d/ipq40xx
	$(INSTALL_DIR) $(1)/etc
	$(INSTALL_DATA) ./files/index.htm $(1)/etc/index.htm
endef

$(eval $(call BuildPackage,ipq40xx))
