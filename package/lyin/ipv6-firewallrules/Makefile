#
# Copyright (C) 2010-2011 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=ipv6-firewallrules
PKG_VERSION:=1
PKG_RELEASE:=2


include $(INCLUDE_DIR)/package.mk

define Package/ipv6-firewallrules
  TITLE:=allow the external network to access the device.
  MAINTAINER:=lyin
  DEPENDS:=
endef

define Package/ipv6-firewallrules/description
allow the external network to access the device.
endef

define Build/Compile
endef

define Package/ipv6-firewallrules/install
	$(INSTALL_DIR) $(1)/etc
	$(INSTALL_BIN) ./ipv6-firewallrules.sh $(1)/etc/ipv6-firewallrules.sh
	$(INSTALL_DIR) $(1)/etc/uci-defaults
	$(INSTALL_BIN) ./ipv6-crontab $(1)/etc/uci-defaults/xxx-ipv6-crontab
endef

define Package/ipv6-firewallrules/postinst
#!/bin/sh
[ -n "$${IPKG_INSTROOT}" ] || sed -i '/ipv6-crontab/d' /etc/crontabs/root
[ -n "$${IPKG_INSTROOT}" ] || echo "0 */1 * * * /etc/ipv6-firewallrules.sh" >> /etc/crontabs/root
[ -n "$${IPKG_INSTROOT}" ] || crontab /etc/crontabs/root
endef

$(eval $(call BuildPackage,ipv6-firewallrules))
