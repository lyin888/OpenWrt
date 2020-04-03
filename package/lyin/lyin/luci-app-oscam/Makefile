include $(TOPDIR)/rules.mk

PKG_NAME:=luci-app-oscam
PKG_VERSION:=4
PKG_RELEASE:=1.1.2
PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)

PO2LMO:=$(TOPDIR)/po2lmo

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
  SECTION:=luci
  CATEGORY:=LuCI
  SUBMENU:=3. Applications
  DEPENDS:=+oscam
  TITLE:=luci-app-oscam
  PKGARCH:=all
endef

define Package/$(PKG_NAME)/description
 oscam web UI
endef

define Build/Prepare
	$(foreach po,$(wildcard ${CURDIR}/i18n/*.po), \
		po2lmo $(po) $(PKG_BUILD_DIR)/$(patsubst %.po,%.lmo,$(notdir $(po)));)
endef

define Build/Compile
endef

define Package/$(PKG_NAME)/postinst
#!/bin/sh 
[ -n "$${IPKG_INSTROOT}" ] || {
	( . /etc/uci-defaults/luci-oscam ) && rm -f /etc/uci-defaults/luci-oscam
	/etc/init.d/oscam enable >/dev/null 2>&1
	exit 0
}
endef

define Package/$(PKG_NAME)/install
	$(CP) ./root/* $(1)
	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/i18n
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/*.lmo $(1)/usr/lib/lua/luci/i18n/
	$(CP) ./luasrc/* $(1)/usr/lib/lua/luci
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
