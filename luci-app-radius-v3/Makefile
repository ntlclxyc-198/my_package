include $(TOPDIR)/rules.mk

PKG_NAME:=luci-app-radius
PKG_VERSION:=0.1
PKG_RELEASE:=1
PKG_MAINTAINER:=Jason Tse <jasontsecode@gmail.com>
PKG_LICENSE:=GPLv2
PKG_LICENSE_FILES:=LICENSE

include $(INCLUDE_DIR)/package.mk

define Package/luci-app-radius
   SECTION:=luci
   CATEGORY:=LuCI
    SUBMENU:=3. Applications
   DEPENDS:=freeradius3 \
   +freeradius3-democerts \
   +freeradius3-mod-always \
   +freeradius3-mod-attr-filter \
   +freeradius3-mod-chap \
   +freeradius3-mod-detail \
   +freeradius3-mod-digest \
   +freeradius3-mod-eap \
   +freeradius3-mod-eap-gtc \
   +freeradius3-mod-eap-leap \
   +freeradius3-mod-eap-md5 \
   +freeradius3-mod-eap-mschapv2 \
   +freeradius3-mod-eap-peap \
   +freeradius3-mod-eap-pwd \
   +freeradius3-mod-eap-tls \
   +freeradius3-mod-eap-ttls \
   +freeradius3-mod-exec \
   +freeradius3-mod-expiration \
   +freeradius3-mod-expr \
   +freeradius3-mod-files \
   +freeradius3-mod-logintime \
   +freeradius3-mod-mschap \
   +freeradius3-mod-pap \
   +freeradius3-mod-preprocess \
   +freeradius3-mod-radutmp \
   +freeradius3-mod-realm \
   +freeradius3-mod-unix
   TITLE:=Freeradius v3 Server Management
   MAINTAINER:=Jason Tse <jasontsecode@gmail.com>
   PKGARCH:=all
endef

define Package/luci-app-radius/description
Freeradius v3 Server Management
endef

define Package/luci-app-radius/conffiles
/etc/config/radius
endef

define Package/luci-app-radius/install
	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_CONF) ./files/config/radius $(1)/etc/config/radius
	$(INSTALL_DIR) $(1)/etc/uci-defaults
	$(INSTALL_BIN) ./files/uci-defaults/luci-radius $(1)/etc/uci-defaults/luci-radius
	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/controller
	$(INSTALL_DATA) ./files/controller/radius.lua $(1)/usr/lib/lua/luci/controller/radius.lua
	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/model/cbi/radius
	$(INSTALL_DATA) ./files/cbi/clients.lua $(1)/usr/lib/lua/luci/model/cbi/radius/clients.lua
	$(INSTALL_DATA) ./files/cbi/users.lua $(1)/usr/lib/lua/luci/model/cbi/radius/users.lua
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_BIN) ./files/lib/radius.sh $(1)/usr/lib/radius.sh
endef

define Package/luci-app-radius/postinst
#!/bin/sh
[ ! -z "$${IPKG_INSTROOT}" ] && exit 0
. /etc/uci-defaults/luci-radius
rm -f /etc/uci-defaults/luci-radius
endef

define Build/Compile
endef

$(eval $(call BuildPackage,luci-app-radius))
