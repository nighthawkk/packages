include $(TOPDIR)/rules.mk

PKG_NAME:=libnpupnp
PKG_VERSION:=4.0.11
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://www.lesbonscomptes.com/upmpdcli/downloads
PKG_HASH:=15b73a5197e649afe44dd15002be131b4b0e20a2b2e9b7ea4a2000b9644fefae

PKG_MAINTAINER:=
PKG_LICENSE:=LGPL-2.1-or-later
PKG_LICENSE_FILES:=COPYING

PKG_INSTALL:=1
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/libnpupnp
  SECTION:=libs
  CATEGORY:=Libraries
  DEPENDS:=+libstdcpp +libexpat +libcurl +libmicrohttpd
  TITLE:=A C++ base UPnP library
  URL:=https://framagit.org/medoc92/npupnp
endef

define Package/libnpupnp/description
npupnp (new pupnp or not pupnp ?) is an UPnP library derived from the
venerable pupnp (https://github.com/pupnp/pupnp), based on its 1.6.x
branch (around 1.6.25).
endef

TARGET_CFLAGS += -flto
TARGET_LDFLAGS += -flto

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include/npupnp
	$(CP) $(PKG_INSTALL_DIR)/usr/include/npupnp/* $(1)/usr/include/npupnp/
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libnpupnp.so* $(1)/usr/lib/
	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/libnpupnp.pc $(1)/usr/lib/pkgconfig/
endef

define Package/libnpupnp/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libnpupnp.so.* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libnpupnp))
