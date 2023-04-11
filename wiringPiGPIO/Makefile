#
# Copyright (C) 2014-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=wiringPiGPIO
PKG_VERSION:=2.70
PKG_RELEASE:=1
PKG_BUILD_DEPENDS := libwiringPi libwiringPiDev

PKG_SOURCE_URL:=https://github.com/WiringPi/WiringPi.git
PKG_SOURCE_PROTO:=git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=1ad03dd3265402baaf0f783708e28c6255032820

include $(INCLUDE_DIR)/package.mk

define Package/wiringPiGPIO
  SECTION:gpio
  CATEGORY:=Utilities
  TITLE:=The gpio command
  DEPENDS:=+libwiringPi +libwiringPiDev
  URL:=http://wiringpi.com/wiringpi-deprecated/
endef

define Package/wiringPiGPIO/description
  A swiss-army knige of GPIO shenanigans.
endef

define Build/Compile 
	$(MAKE) -C $(PKG_BUILD_DIR)/gpio\
	CC=$(TARGET_CC) \
	DESTDIR="$(STAGING_DIR)/usr" PREFIX="/"

endef

define Package/wiringPiGPIO/install
	$(INSTALL_DIR) $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/gpio/gpio	$(1)/usr/bin/
endef

$(eval $(call BuildPackage,wiringPiGPIO))
