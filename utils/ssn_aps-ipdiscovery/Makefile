include $(TOPDIR)/rules.mk

PKG_NAME:=ssn_ipdiscovery
PKG_VERSION:=1.0.1
PKG_RELEASE:=5
PKG_MAINTAINER:=SSN 
PKG_LICENSE:=UNDEFINED

include $(INCLUDE_DIR)/package.mk

PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

TARGET_LDFLAGS+= \
		-Wl,-rpath-link=$(STAGING_DIR)/usr/lib

define Package/ssn_ipdiscovery
		SECTION:=utils
		CATEGORY:=Utilities
		TITLE:=SSN ip autodetect	util
		URL:=https://gitlab.stusta.de/stustanet/ssn_aps-ipdiscovery
		MENU:=1
endef

define Package/ssn_ipdiscovery/description
IP autodetect
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) ./src/* $(PKG_BUILD_DIR)/
endef

define Build/Configure
endef

define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR) $(TARGET_CONFIGURE_OPTS)
endef

define Package/ssn_ipdiscovery/install
	$(INSTALL_DIR) $(1)/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/ssn_ipdiscovery $(1)/bin/
endef

$(eval $(call BuildPackage,ssn_ipdiscovery))

