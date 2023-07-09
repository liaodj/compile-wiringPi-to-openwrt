#
# Copyright (C) 2014-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=libwiringPi
PKG_VERSION:=2.70
PKG_RELEASE:=1
# PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)
# PKG_BUILD_DIR:=$(BUILD_DIR)/WiringPi
# PKG_INSTALL:=1

PKG_SOURCE_URL:=https://github.com/WiringPi/WiringPi.git
PKG_SOURCE_PROTO:=git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=f97a6230160b819e6daea7eb242404afa708e421
PKG_MIRROR_HASH:=cfb981477cbbf9b7371ddb76fbd4a98ecf2298a66cd134b4bdd94e4eb73149cb

include $(INCLUDE_DIR)/package.mk

define Package/libwiringPi
  SECTION:gpio
  CATEGORY:=Libraries
  TITLE:=Wiring Compatable library for the Raspberry Pi
  URL:=http://wiringpi.com/wiringpi-deprecated/
endef

define Package/libwiringPi/description
  Wiring Compatable library for the Raspberry Pi
endef

# define Build/Prepare
#   tar zxf ./WiringPi.tar.gz -C $(BUILD_DIR)
# endef

define Build/Compile 
	$(MAKE) -C $(PKG_BUILD_DIR)/wiringPi\
	CC=$(TARGET_CC)
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/wiringPi/*.h $(1)/usr/include/
	$(INSTALL_DIR) $(1)/usr/lib/
	$(CP) $(PKG_BUILD_DIR)/wiringPi/libwiringPi.so.$(PKG_VERSION)	$(1)/usr/lib/
	ln -sf ./libwiringPi.so.$(PKG_VERSION)	$(1)/usr/lib/libwiringPi.so
endef

define Package/libwiringPi/install
	$(INSTALL_DIR) $(1)/usr/lib/
	$(CP) $(PKG_BUILD_DIR)/wiringPi/libwiringPi.so.$(PKG_VERSION)	$(1)/usr/lib/
	ln -sf ./libwiringPi.so.$(PKG_VERSION)	$(1)/usr/lib/libwiringPi.so
endef

$(eval $(call BuildPackage,libwiringPi))


