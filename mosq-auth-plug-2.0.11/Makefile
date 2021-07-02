include $(TOPDIR)/rules.mk

PKG_NAME:=mosq-auth-plug
PKG_RELEASE:=2.0.11

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk

define Package/mosq-auth-plug
	SECTION:=utils
	CATEGORY:=Utilities
	TITLE:=Hello mosquitto-auth-plug!!!
	DEPENDS:= +libopenssl +libmysqlclient +libsqlite3 +libcurl +libmosquitto
endef

define Package/mosq-auth-plug/description
	It's my first package demo.
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) ./src/* $(PKG_BUILD_DIR)/
endef

define Package/mosq-auth-plug/install
	$(INSTALL_DIR) $(1)/usr/local/lib
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/$(PKG_NAME).so $(1)/usr/local/lib/
#	$(CP) $(PKG_BUILD_DIR)/$(PKG_NAME).so $(1)/usr/local/lib/
endef

$(eval $(call BuildPackage,mosq-auth-plug))
