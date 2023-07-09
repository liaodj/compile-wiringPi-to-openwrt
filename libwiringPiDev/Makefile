#
# Copyright (C) 2014-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=libwiringPiDev
PKG_VERSION:=2.70
PKG_RELEASE:=1
PKG_BUILD_DEPENDS:=libwiringPi

PKG_SOURCE_URL:=https://github.com/WiringPi/WiringPi.git
PKG_SOURCE_PROTO:=git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=1ad03dd3265402baaf0f783708e28c6255032820

include $(INCLUDE_DIR)/package.mk

define Package/libwiringPiDev
  SECTION:gpio
  CATEGORY:=Libraries
  TITLE:=wiringPi device - A wiring library for the Raspberry Pi
  URL:=hhttp://wiringpi.com/wiringpi-deprecated/
endef

define Package/libwiringPiDev/description
  wiringPi device - A wiring library for the Raspberry Pi
endef


define Build/Compile 
	$(MAKE) -C $(PKG_BUILD_DIR)/devLib\
	CC=$(TARGET_CC)
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/devLib/*.h $(1)/usr/include/
	$(INSTALL_DIR) $(1)/usr/lib/
	$(CP) $(PKG_BUILD_DIR)/devLib/libwiringPiDev.so.$(PKG_VERSION)	$(1)/usr/lib/
	ln -sf ./libwiringPiDev.so.$(PKG_VERSION)	$(1)/usr/lib/libwiringPiDev.so
endef

define Package/libwiringPiDev/install
	$(INSTALL_DIR) $(1)/usr/lib/
	$(CP) $(PKG_BUILD_DIR)/devLib/libwiringPiDev.so.$(PKG_VERSION)	$(1)/usr/lib/
	ln -sf ./libwiringPiDev.so.$(PKG_VERSION)	$(1)/usr/lib/libwiringPiDev.so
endef

$(eval $(call BuildPackage,libwiringPiDev))
