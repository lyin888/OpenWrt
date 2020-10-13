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
  DEPENDS:=@TARGET_ipq40xx \
    +TARGET_ipq40xx:lm-sensors
endef

define Package/ipq40xx/description
  A luci autoconfig hotplug script.
endef

define Build/Compile
endef

define Package/ipq40xx/install
        $(INSTALL_DIR) $(1)/etc
	$(INSTALL_DATA) ./files/arm/index.htm $(1)/etc/index.htm
	$(INSTALL_DIR) $(1)/etc/uci-defaults
	$(INSTALL_BIN) ./files/arm/090-cover-index_htm $(1)/etc/uci-defaults/090-cover-index_htm
	$(INSTALL_DIR) $(1)/sbin
	$(INSTALL_BIN) ./files/arm/sbin/cpuinfo $(1)/sbin/cpuinfo
endef

$(eval $(call BuildPackage,ipq40xx))
