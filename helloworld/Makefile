include $(TOPDIR)/rules.mk

PKG_NAME:=helloworld
PKG_RELEASE:=1

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk

define Package/helloworld
	SECTION:=utils
	CATEGORY:=Utilities
	TITLE:=Hello world!!!
	#DEPENDS:=+libwebsockets +libsqlite3 +libjson-c
endef

define Package/helloworld/description
	It's my first package demo.
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) ./src/* $(PKG_BUILD_DIR)/
endef

define Package/helloworld/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/$(PKG_NAME) $(1)/usr/sbin
endef

$(eval $(call BuildPackage,helloworld))