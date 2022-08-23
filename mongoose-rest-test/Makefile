##############################################
# OpenWrt Makefile 
##############################################
include $(TOPDIR)/rules.mk
 
PKG_NAME:=mongoose-rest-test
PKG_VERSION:=1.0.0
PKG_RELEASE:=1
 
# This specifies the directory where we're going to build the program. 
# The root build directory, $(BUILD_DIR), is by default the build_mipsel
# directory in your OpenWrt SDK directory
 
PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)

# Source settings (i.e. where to find the source codes)
# This is a custom variable, used below
SOURCE_DIR:=./src
 
include $(INCLUDE_DIR)/package.mk
 
define Package/mongoose-rest-test
	SECTION:=utils
	CATEGORY:=Utilities
	TITLE:=mongoose-rest-test
	DEFAULT:=y
	VERSION:=$(PKG_VERSION)
endef

define Package/mongoose-rest-test/description
	Mongoose rest api test.
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) $(SOURCE_DIR)/* $(PKG_BUILD_DIR)/
endef
define Build/Configure
endef
define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR) \
		CC="$(TARGET_CC)" \
		CFLAGS="$(TARGET_CFLAGS) -Wall" \
		LDFLAGS="$(TARGET_LDFLAGS)"
endef

define Package/mongoose-rest-test/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_DIR) $(1)/usr/bin/mg-test-web-root
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mongoose-rest-test $(1)/usr/bin/
	$(CP) ./mg-test-web-root/* $(1)/usr/bin/mg-test-web-root
endef

$(eval $(call BuildPackage,mongoose-rest-test))
