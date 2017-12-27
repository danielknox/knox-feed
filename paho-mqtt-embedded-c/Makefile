# Author: Daniel Knox <d.knox@kent.ac.uk>

include $(TOPDIR)/rules.mk

PKG_NAME:=paho.mqtt.embedded-c
PKG_VERSION:=v1.3.0
PKG_RELEASE:=v1.0.0
PKG_MAINTAINER:=Dan Knox <d.knox@kent.ac.uk>

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=git://github.com/kersing/paho.mqtt.embedded-c.git
PKG_SOURCE_VERSION:=8ccbef7c64b74a492bfc8d95ac65cb7bab452f3e
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
# We override "packagename-packageversion", because
# other packages reference to the build dir of this package
PKG_SOURCE_SUBDIR:=$(PKG_NAME)
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

PKG_FIXUP:=autoreconf

include $(INCLUDE_DIR)/package.mk

define Package/paho.mqtt.embedded-c
  TITLE:=Paho Mqtt Embedded C
  SECTION:=libs
  CATEGORY:=Libraries
endef

define Package/paho.mqtt.embedded-c/description
  Runtime library for mqtt.
endef

define Package/paho.mqtt.embedded-c/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_BUILD_DIR)/build/output/libpaho-embed-mqtt3c.* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,paho.mqtt.embedded-c))
