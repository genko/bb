#
# Copyright (C) 2008-2011 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=sispmctl
PKG_VERSION:=3.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=@SF/$(PKG_NAME)
PKG_MD5SUM:=eca3d5803a29617432ef9f609be59bad

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/sispmctl
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Silver Shield PM Control for Linux
  URL:=http://sispmctl.sourceforge.net/
  DEPENDS:=+libusb
endef

define Package/sispmctl/description
 The sispmctl tool can control Gembird SIS-PM Silver Shield
 programmable power outlet strips (also known under the name
 Revolt Intelli-Plug) from the command line.
 .
 It can be used to switch on or off any of the programmable
 power sockets of the SIS-PM via USB. It can also show the
 current status of each power socket, and it can handle
 multiple SIS-PM devices, too.
endef

CONFIGURE_ARGS += \
	--enable-webless \
	--disable-dependency-tracking

define Package/sispmctl/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/$(PKG_NAME) $(1)/usr/bin/
endef

$(eval $(call BuildPackage,sispmctl))
